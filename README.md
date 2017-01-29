# orron
World which has authority center for all the data in galaxy (http://starwars.wikia.com/wiki/Orron_III)

Install
=======

Requires Python 2.7, 3.4, or 3.5. Requires Django 1.7.1 or higher.

Set up a Django project with the following:

```bash
$ pip install django
$ django-admin startproject project
```

More information [here](https://docs.djangoproject.com/en/1.10/intro/tutorial01/).

Install with pip from github:

``pip install django-sql-explorer``

Add to your `INSTALLED_APPS`, located in the `settings.py` file in your project folder:

``INSTALLED_APPS = (
...,
'explorer',
...
)``

## Reference:
https://github.com/groveco/django-sql-explorer
