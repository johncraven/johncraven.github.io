---
title: "Todo Update: Field properties, Comments and Styling"
slug: "todo-2"
date: 2025-06-22T13:02:50-04:00
draft: false
categories:
- tech
tags:
- django
- web
- django-todo
---

I've been playing around with extending the [toy Django app]({{<ref "/posts/2025-06-17-todo-site.md" >}}) I was working on. I wanted to focus on getting more backend experience with Django while also getting more understanding for web dev basics for HTML/CSS/JS, so I restricted myself to Django and vanilla CSS/JS for now.

## Current state

![image](site-example.gif#center)

## New features

* Added some basic CSS container and form styling with a little neubrutalism inspiration.
* Added more properties on the default todo items; due dates, descriptions, priority
* The list view on the homepage includes the description and flags for overdue and high priority items
* The detail page now has a basic comment section, making use of the `django.contrib.humanize` package to format dates into relevant strings like "now" or "an hour ago"
* And of course, additions to the test suite for new functionality

## Process

This time around I am trying to take a more project-oriented approach to learning, and integrating more LLM tools into my workflow. Since I'm doing this to learn on my own I'm leaning more on the side of using the llm tools to guide me rather than edit code directly.

This time I started by using anthropic's Claude to discuss some basic goals and prioritize features. When I would get stuck I would try to do a bit of debugging with tools in my IDE or the browser devtools, then if I was stuck I would usually try explaining the general issue with the LLM to guide me. It has been interesting that even when the LLM suggestions are not accurate, I found that I enjoyed not needing to context switch through project documentation, stack overflow, or reddit comments. In particular the LLM chat seemed to go a great job in answering the "what are my options to accomplish X" or "I'm trying to do X but it isn't working, am I going about this the right way".

A few things Claude helped me with...

* Finding some conflicting CSS properties after adding snippets from my CSS files in the chat context
* Setting up the django tests to work with VS Code's native test runner
* Configuring template linting with djlint
* Tinkering with django's generic class based view properties and refactoring some views into function based views

Next up I'll need to look at adding more JS on the site.
