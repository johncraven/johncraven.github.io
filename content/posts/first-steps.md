---
title: "First Steps in Django"
date: 2022-01-11T13:14:46-05:00
draft: False
series:
    - django-journey
---

### Starting out
I've been interested in building more web development skills for a while now. I know some basic HTML/CSS, not as much JS. In particular I wanted to learn more about back end or full stack type web development, since I'm more interested in how to translate business logic into tools than presentation or interaction in front-end focused web development.

[Django](https://www.djangoproject.com/) seemed like a good fit for me, it's a full-stack framework in the vein of Rails or Laravel and it's built in python. Django has a "batteries included" philosophy and includes a lot of the tooling you need for a simple web app right off the bat; an ORM to define and interact with your database, url routing, different types of views, and a templating system for html or other files. I thought django was a good fit for me since I already knew some python, and I was hoping the "batteries included" style of framework would stave off some analysis-paralysis of trying to navigate a jungle of different tools.

As an aside, I played a little bit with two other python based frameworks; [Flask](https://flask.palletsprojects.com/en/2.0.x/) and [FastAPI](https://fastapi.tiangolo.com/). Flask is another mainstay in python web frameworks but it's designed to be very minimal, and you include tools as needed. After running through an excellent guide from [Miguel Grinberg](https://courses.miguelgrinberg.com/) I was surprised how much parity there was between his example and Django, but with more flexibility. FastAPI is very cool, especially if you want to through a quick API over some python code you've already written, but didn't fit the bill for the type of full stack development I was looking for.


### Training wheels
OK, so I decided Django was the sweet spot, now what? I'll admit I fell into the trap of reading too much about it before building my own projects. I went through the tutorial on the [django website](https://docs.djangoproject.com/en/4.0/intro/tutorial01/), read through [Django for Beginners](https://djangoforbeginners.com/), and finally [Wedge of Django](https://www.feldroy.com/books/a-wedge-of-django) even though each of those stress to get out and build stuff at the end. But the positive side of reading through those is that I got introduced to a lot of things I might not have found out on my own. Things like deploying on heroku, making factories for tests, seperating out environment variables for local dev and production didn't seem as daunting.

I want to start practicing with some small projects before I tackle some of the bigger projects I have in mind. The classic first project is a To-Do app, which sounds like a good place to start.
