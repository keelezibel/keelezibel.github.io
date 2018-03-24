---
layout: single
title: Heroku shortcuts
categories: Coding
tags: 
- Heroku
---

Below are some shortcuts for setting up a python project.
<br />
<br />

Login to heroku with credentials
```
heroku login
```

Create a new heroku app
```
heroku create {{appname}}
```

Deploy code at root of project
```
heroku push origin master
```

Instantiate one instance of app
```
heroku ps:scale web=1
```

Shortcut to open app url
```
heroku open
```

Read logs
```
heroku logs --tail
```

Define a Procfile at root 
```
web: gunicorn {{app}}.wsgi --log-file -
```

Specify dependencies in requirements.txt
```
dj-database-url==0.4.1
Django==1.11.1
gunicorn==19.6.0
psycopg2==2.6.2
whitenoise==3.2
```

Collect all static assets
```
python manage.py collectstatic
```

Settings for collecting static assets in app/settings.py
```
PROJECT_ROOT = os.path.dirname(os.path.abspath(__file__))

STATIC_ROOT = 'staticfiles'
STATIC_URL = '/static/'

# Extra places for collectstatic to find static files.
STATICFILES_DIRS = (
    os.path.join(PROJECT_ROOT, 'static'),
)

# Simplified static file serving.
# https://warehouse.python.org/project/whitenoise/
STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'


MIDDLEWARE_CLASSES = (
    # Simplified static file serving.
    # https://warehouse.python.org/project/whitenoise/
    'whitenoise.middleware.WhiteNoiseMiddleware',
    ...
```

Push to heroku
```
git push origin master
git push heroku master
```
