# Django 4.2 Tutorial

https://docs.djangoproject.com/ja/4.2/intro/

## Install

```sh
poetry init

Package name [django_4.2_tutorial]:
Version [0.1.0]:
Description []:
Author [dhythm <yuta.okada.20@gmail.com>, n to skip]:
License []:
Compatible Python versions [^3.9]:
Would you like to define your main dependencies interactively? (yes/no) [yes]
Package to add or search for (leave blank to skip):
Would you like to define your development dependencies interactively? (yes/no) [yes]
Package to add or search for (leave blank to skip):
Do you confirm generation? (yes/no) [yes]
```

Install django by,

```sh
poetry install

poetry add Django@4.2
poetry run python -m django --version
```

Install development tools by,

```sh
poetry add --dev black isort autoflake
```

## Create a project

```sh
poetry run django-admin startproject mysite

poetry run python manage.py runserver
```

## Create Polls application

```sh
cd mysite
poetry run python manage.py startapp polls
touch polls/urls.py
```
