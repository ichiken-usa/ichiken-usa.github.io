---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
description: description
menu:
  sidebar:
    name: Test1
    identifier: test1
    parent: hugo
    weight: 10
hero: hero.svg
tags:
- Hugo
- Blog
categories:
- Development
draft: true
---