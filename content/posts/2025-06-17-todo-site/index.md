---
title: "Simple Todo Site"
slug: "todo-1"
date: 2025-06-17T19:53:37-04:00
draft: false
categories:
- tech
tags:
- django
- web
- django-todo
---

I have been working in an IT management role for a few years now, primarily focused on data engineering and integrations with analytical instrumentation. Unfortunately, I rarely get the chance to develop hands-on coding skills at work, so I thought it would be fun to take up some side projects and tinker around. To get started I made a simple to-do website with Django. The site is basic CRUD functionality just to help jog my memory on how everything fits together.

If you haven't head of [Django](https://www.djangoproject.com/), its a python web framework that is pitches as being "batteries included". It the core things you might want in a backend framework built in - ORM, auth, routing, template rendering, and a good ecosystem of supporting packages. I thought it would be a good fit to start with Django because I had some previous exposure to the framework, I know a decent amount of python, and Django's feature set seems like a good fit to build out little demo sites and proof of concepts for work.

![image](site_example.gif#center)

The core of the site really comes down to requests being routed to configuring a "model" that defines the database tables and relationships for data in the app, "views" which take those models and business logic to render "templates"

The models file here only has one class, which translates into one database table with a relation to a separate user model. Django comes set up using sqlite but also has support for postgres, mysql and a few other rdbms flavors.

```python
# tasks/models.py
from django.db import models
from django.urls import reverse


class Task(models.Model):
    title = models.CharField(max_length=50, null=False)
    is_complete = models.BooleanField(default=False, null=False)
    author = models.ForeignKey(
        "users.CustomUser", on_delete=models.CASCADE, related_name="tasks", default=""
    )

    def __str__(self):
        return self.title if len(self.title) < 31 else self.title[:30] + "..."

    def get_absolute_url(self):
        return reverse("task_detail", kwargs={"pk": self.pk})
```

For the views here I kept them simple and used the generic class based views. I had a few issues finding the first fields on some of these but a mix of trial and error with the debug responses from the development server and [Classy Class Based Views](https://ccbv.co.uk/) helped out. I ran into a few issues on setting up some custom logic in forms and needed to set up the debug options in vscode to make sure I was using the right methods.

```python
# tasks/views.py 
from django.shortcuts import render
from django.views.generic import DetailView, DeleteView, UpdateView, CreateView
from django.urls import reverse_lazy
from django.contrib.auth.decorators import login_required

from .models import Task
from .forms import TaskUpdateForm


@login_required
def homepage_view(request):
    tasks = Task.objects.filter(author=request.user).order_by("is_complete")
    return render(
        request,
        template_name="home.html",
        context={
            "tasks": tasks,
        },
    )


class TaskCreate(CreateView):
    model = Task
    fields = ["title"]
    template_name = "task_new.html"
    success_url = reverse_lazy("home")

    def form_valid(self, form):
        form.instance.author = self.request.user
        return super().form_valid(form)

....
```

Those views couple with some simple html templates to render out forms and links to different parts of the site. Here's an example template...

```html
{% comment %} templates/task_new.html {% endcomment %}
{% extends "base.html" %}

{% block title %}New Task{% endblock title %}

{% block main %}
<h1>Create task</h1>
<form  class="update-form" action="" method="post">
    {% csrf_token %}
    {{form.title}}
    <button id="update-submit" type="submit">Update</button>
</form>
{% endblock main %}
```

The most complicated part of this example was getting auth set up. I used the basic password authentication built in with django but followed a guide from William Vincent on [how to set up a custom user model and profile](https://learndjango.com/tutorials/django-custom-user-model). From there I just needed to wire up the right routing, views and templates to get the custom user model working properly.

Overall it was a good chance to knock some of the rust off and start getting reacquainted with basic web development.
