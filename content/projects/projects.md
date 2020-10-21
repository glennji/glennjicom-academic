+++
# A Projects section created with the Portfolio widget.
widget = "portfolio"
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 45 # Order that this section will appear.

title = "Projects"
subtitle = ""

[content]
  # Page type to display. E.g. project.
  page_type = "project"
  
  # Filter toolbar (optional).
  # Add or remove as many filters (`[[content.filter_button]]` instances) as you like.
  # To show all items, set `tag` to "*".
  # To filter by a specific tag, set `tag` to an existing tag name.
  # To remove toolbar, delete/comment all instances of `[[content.filter_button]]` below.
  
  # Default filter index (e.g. 0 corresponds to the first `[[filter_button]]` instance below).
  filter_default = 0
  
  [[content.filter_button]]
    name = "All"
    tag = "*"
  
  [[content.filter_button]]
    name = "Completed"
    tag = "completed"
    
  [[content.filter_button]]
    name = "In Progress"
    tag = "inprogress"
    
  [[content.filter_button]]
    name = "Someday, maybe"
    tag = "someday"
  
  [[content.filter_button]]
    name = "Hardware"
    tag = "hardware"
    
  [[content.filter_button]]
    name = "Software"
    tag = "software"

  [[content.filter_button]]
    name = "Professional"
    tag = "professional"
    
  [[content.filter_button]]
    name = "Hobby"
    tag = "hobby"

[design]
  # Choose how many columns the section has. Valid values: 1 or 2.
  columns = "1"

  # Toggle between the various page layout types.
  #   1 = List
  #   2 = Compact
  #   3 = Card
  #   5 = Showcase
  view = 3

  # For Showcase view, flip alternate rows?
  flip_alt_rows = true

[design.background]
  # Apply a background color, gradient, or image.
  #   Uncomment (by removing `#`) an option to apply it.
  #   Choose a light or dark text color by setting `text_color_light`.
  #   Any HTML color name or Hex value is valid.
  
  # Background color.
  # color = "navy"
  
  # Background gradient.
  # gradient_start = "DeepSkyBlue"
  # gradient_end = "SkyBlue"
  
  # Background image.
  image = "projects-bg2.jpg"
  image_darken = 0.8

  # Text color (true=light or false=dark).
  text_color_light = true  
  
[advanced]
 # Custom CSS. 
 css_style = ""
 
 # CSS class.
 css_class = ""
+++
I've done a bunch of projects over the years, but almost never remember to either write them up or keep a copy of the code. As such, this section is pretty bare (for now), but I am trying to fill it out with the new stuff I might work/play on.
