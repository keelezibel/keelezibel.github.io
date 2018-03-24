---
layout: single
title: Django web framework
categories: Coding
tags: 
- Django
---

## Start a new Django Project
```
mkdir django-tutorials
cd django-tutorials
django-admin startproject mysite
```

The directory breakdown is as follows:
```
django-tutorials
|
|---mysite
|------mysite
|--------- __init__.py
|--------- settings.py
|--------- urls.py
|--------- wsgi.py
|------manage.py
```

### Explanation
- <mark>__init__.py</mark> Specifies to treat the folder as a package
- <mark>settings.py</mark> Note: New applications have to be manually added under INSTALLED_APPS.
- <mark>urls.py</mark> Controller
- 

## Check if project is working locally
```
python manage.py runserver
```
This will initiate the development server. Head over to a browser and access localhost:8000. You should see a welcome page.
<br /><br />
Next, we will start to add apps to the site. In this case, we add webapp.
```
python manage.py startapp webapp
```
The directory breakdown is as follows:
```
django-tutorials
|
|---webapp
|--- migrations
|--- __init__.py
|--- admin.py
|--- apps.py
|--- models.py
|--- tests.py
|--- views.py
```
<mark> models.py</mark> specify the database information and metadata.
<mark> views.py</mark> controls what your end-user sees and feels.
<mark> urls.py</mark> controls what's served based on URL patterns.