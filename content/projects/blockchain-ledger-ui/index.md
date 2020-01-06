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
3. Programmatic mappers
3. Reactive REST

## GraphQL
As mentioned, the system manipulates a number of "entities": users, companies, securities, participants, etc. We've built a Java-based microservice that provides a GraphQL API for the query and mutation of each of these using a library called `graphql-spqr`.

With `graphql-spqr`, we simply annotate some Spring components: `@GraphQLApi` on the component class, and one of `@GraphQLQuery`, `@GraphQLMutation` or `@GraphQLSubscription` on each method we want to expose. `graphql-spqr` discovers these and generates both the `GraphQLSchema` and a `GraphQLType` for each input parameter or return type. By using our models, we can quickly iterate on the schema and API e.g. adding a new field to the model immediately makes it part of the schema and available for querying upon.

## JSON schema form rendering


## Programmatic mappers

## Reactive REST
