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

## Set Database

Move to the rood directory.
ref: https://hub.docker.com/_/postgres

```sh
touch docker-compose.yml

docker compose up -d
docker compose down --remove-orphans

docker exec -it django_42_tutorial-db-1 psql -U postgres postgres
```

Set up the database by,

```sh
poetry run python manage.py makemigrations polls
poetry run python manage.py sqlmigrate polls 0001
poetry run python manage.py migrate
```

## Use Django Admin

```sh
poetry run python manage.py createsuperuser

Username (leave blank to use 'dhythm'): admin
Email address: admin@example.com
Password: ********
Password (again): ********
Bypass password validation and create user anyway? [y/N]: y
```

```sh
poetry run python manage.py runserver
```

Access to Django Admin by http://127.0.0.1:8000/admin/

Get paths of default django source files by,

```sh
poetry run python -c "import django; print(django.__path__)"
```

## Testing

```sh
touch polls/tests.py

poetry run python manage.py test polls
```
