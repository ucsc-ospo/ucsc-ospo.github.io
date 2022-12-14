---
widget: portfolio 
headless: true  # This file represents a page section.

# Put Your Section Options Here (title, background, etc.) ...
title: "2022 Projects"
subtitle: "Return to [new projects](/osre/#projects)"

# Position of this section on the page
weight: 10

content:
  # Choose which content to display in the widget
  filters:
    # Folders to display content from
    folders:
      - project
    # Replace this tag to the current year (e.g. osre23)
    tags:
      - osre22
    # Uncomment below to exclude content with specific tags:
#    exclude_tags:
#      - preface    
    # Uncomment below to show specific Hugo Page kinds
    kinds:
      - page
#      - section

  # Field to sort by, such as Date or Title
  sort_by: 'Title'
  sort_ascending: true

  # Filter toolbar (optional).
  # Add or remove as many filters (`filter_button` instances) as you like.
  # To show all items, set `tag` to "*".
  # To filter by a specific tag, set `tag` to an existing tag name.
  # To remove toolbar, delete/comment all instances of `filter_button` below.
  filter_button:
    - name: All
      tag: '*'
    - name: UC Mentors
      tag: uc
    - name: Reproducibility
      tag: reproducibility
    - name: Hide
      tag: hidden

  # Default filter toolbar button (e.g. 0 corresponds to the first `filter_button` instance above)
  filter_default: 0
design:
  # Choose a listing view
  view: compact
  # Choose how many columns the section has. Valid values: '1' or '2'.
  columns: '2'
---

