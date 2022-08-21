---
title: Interview Tips
date: 2021-08-18 00:00:00 -500
categories: [Backend]
tags: [Django] # TAG names should always be lowercase
img_path: /assets/posts/
---

## Create a project

`$ django-admin startproject mysite`

## Run the server

`$ python manage.py runserver`

## Visit

[http://127.0.0.1:8000/](http://127.0.0.1:8000/)

## Create an app

> What’s the difference between a project and an app? An app is a web application that does something – e.g., a blog system, a database of public records or a small poll app. A project is a collection of configuration and apps for a particular website. A project can contain multiple apps. An app can be in multiple projects.

`$ python manage.py startapp polls`

## Create tables for the pre-installed apps

`$ python manage.py migrate`

## Define tables in the model.py under the app folder

In `polls/model.py`:

```py
from django.db import models


class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')


class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
```

## Activate the model

1. Include the app in the project
   In `mysite/settings.py`, add `'polls.apps.PollsConfig'` into `INSTALLED_APPS`

2. Save the changes to `models` as a migration

   > Migrations are how Django stores changes to your models (and thus your database schema) - they’re files on disk.

   `$ python manage.py makemigrations polls `

3. Check the corresponding SQL commands for a migration (Optional)

   `$ python manage.py sqlmigrate polls 0001`

4. Synchronize the changes

   `$ python manage.py migrate`

## Steps to make model changes

1. Change your models (in **models.py**).
2. Run `python manage.py makemigrations` to create migrations for those changes
3. Run `python manage.py migrate` to apply those changes to the database.

## Create admin

`$ python manage.py createsuperuser`
