---
title: Blog
summary: My blogs
type: landing

cascade:
  - _target:
      kind: page
    params:
      show_breadcrumb: true

sections:
  - block: collection
    id: blog
    content:
      title: Blog
      filters:
        folders:
          - blog
    design:
      view: article-grid
      columns: 2
---