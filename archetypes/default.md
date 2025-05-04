---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
description: description
menu:
  sidebar:
    name: Category
    identifier: category
    parent: parent-category
    weight: 10
hero: images/forest.jpg
tags:
- Blog
categories:
- Basic
draft: true
---