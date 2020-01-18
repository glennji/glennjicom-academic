---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Blockchain Ledger UI"
subtitle: ""
summary: ""
authors: []
tags: ["inprogress", "professional", "software"]
categories: []
date: 2019-11-14T00:21:06+11:00
lastmod: 2019-11-14T00:21:06+11:00
featured: false
crosslink: "true"
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---
This (ongoing) project is to provide a front-end to a blockchain-based ledger for post-trade services including clearing, settlement and asset registration. It consists of a Java-based backend (microservices) and a React frontend, and is deployed to a Kubernetes cluster (PKS).

The ledger provides GRPC endpoints (and technically protobuffs)  that allow us to submit messages, or "exercise non-consuming contracts" as it happens. As per "recommended approach", we are using a Java API which was generated from the underlying ledger source language, which means a bunch of static and impenetrable classes representing the "entities" of the system, as well as a compile-time dependency on the API library.

A couple of things played into our design of the system which are worth mentioning as they steered many of our choices upfront. First, we are working to a very ambitious deadline — I'm actually using Maven build-time to write this project description — and are dependent on subsystems that haven't been designed, let alone implemented. We also expect the ledger API to change during development, with new versions changing any and all aspects of the underlying entities and endpoints.

As such, our first decision was to decouple the ledger representation (Java classes) from our model. For each entity we need to manipulate via the front- or backend, we have a corresponding "model object":

> e.g. say we have a `UserTokenContainer` in the ledger API that represents a current user session and all permissions that user may have. As this API can mutate — adding and removing fields, changing types, etc — we instead immediately convert it to a `User` object which consists only of primitive and near-primitive (nested) types. This _DTO_ (data transfer object) can then be safely converted and transmitted across microservices until it is converted back to an API-sourced object when required[^1].

[^1]: Although not, interestingly enough, the original `UserTokenContainer`. The API given requires a different `Message` object for any mutations we may want to perform on a system entity.

(Note that I've been heavily into the backend service development, and so I'm biased towards those.)

There are a couple of interesting things we can do with these models now:

1. GraphQL
2. JSON schema form rendering
3. Reactive REST
4. Reactive Message handling
5. Mapping

## GraphQL
As mentioned, the system manipulates a number of "entities": users, companies, securities, participants, etc. We've built a Java-based microservice that provides a GraphQL API for the query and mutation of each of these using a library called `graphql-spqr`.

With `graphql-spqr`, we simply annotate some Spring components: `@GraphQLApi` on the component class, and one of `@GraphQLQuery`, `@GraphQLMutation` or `@GraphQLSubscription` on each method we want to expose. `graphql-spqr` discovers these and generates both the `GraphQLSchema` and a `GraphQLType` for each input parameter or return type. By using our models, we can quickly iterate on the schema and API e.g. adding a new field to the model immediately makes it part of the schema and available for querying upon.

## JSON schema form rendering

## Reactive REST (Webflux)

## Reactive message handling (RxJava)

The ledger provides us with a number of "clients" which are implemented with RxJava and allow for non-blocking, reactive stream processing — we are particularly concerned with the `CommandClient` and the `TransactionClient`.

* `CommandClient` allows messages to be submitted to the ledger.
*  `TransactionClient` allows us to receive a (filtered) stream of transactions

Transactions contain events representing changes on the ledger, and as the clients are reactive it is reasonably easy to filter, map and process the streams themselves.

When an endpoint is called that requests a particular ledger activity, we have a few things to do:

1. Construct an appropriate call to the ledger, including a `messageId` that allows for correlation
2. Connect a "listener" to the transaction stream that is waiting for any matching "response" messages
3. Submit the call to the ledger
4. Receive a matching "response" message and decode it.

For now, the transaction stream "listener" will forward the (decoded) response message to the initiating user via a reactive REST endpoint (`/onNotification`), which in turn is used to drive a GraphQL subscription endpoint of the same name. In the near future, we will need to persist and manage notifications in such a way as to allow users to e.g. submit requests, log out, change machines, reconnect.

## Mapping

One of the ways the ledger communicates is via ISO20022-like messages. These are represented by corresponding protobuf types, which are converted into Java classes that we use via a "client stub" library i.e. JAR.

In order to keep things together (i.e. the principle of encapsulation), we have created a set of `CommandSet` classes for each model type: `EntityCommandSet`, `ParticipantCommandSet`, etc. Each of these implements:

1. Submission methods (`create()`, `update()` and/or `delete()`) - returns a `List<Command>` containing the appropriate ISO-like message hierarchies to perform the action. This list is submitted to the ledger via a non-consuming contract.
2. Response handler - Each message that is submitted has a set of possible response messages, which represent e.g. "success", "failure" or "deferred". As mentioned, after we submit we "watch" the outgoing transaction stream looking for related messages. When found, they are passed to the message handler function which decodes them into a message (`CommandStatus`) for the front-end.

Unfortunately, ISO20022's XML structure leads to deeply nested object trees which we need to both construct (when submitting messages) and unpack (when processing the outcome). This isn't particularly pretty code, and is definitely something that I'd love to revisit, but in the meantime it means that we have a lot of message-specific handling in each `CommandSet` class.

Further, some (most?) messages can be used to create/update/delete different underlying types, so there is an amount of duplication required for both submission and handling.

In summary, this means that each "type" that we wish to manipulate will require a `CommandSet` subclass that knows everything about the ISO messages, and is regretably "brittle":

* Should the ISO message itself change (e.g. ledger version upgrade), the `CommandSet` for each type that uses the message will also need to be changed. 
* Should the ledger API change which messages are being used, the `CommandSet` will also need to be changed
* If the meaning of fields or location of particular data inside an ISO message changes, the `CommandSet` for each type will need to be updated correspondingly.