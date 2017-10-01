---
layout: single
title: Django web framework
categories: Web
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
- <mark>settings.py</mark>