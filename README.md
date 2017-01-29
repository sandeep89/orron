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

Add the following to your urls.py (all Explorer URLs are restricted via the EXPLORER_PERMISSION_VIEW and EXPLORER_PERMISSION_CHANGE settings. See Settings section below for further documentation.):

``url(r'^explorer/', include('explorer.urls')),``

Run migrate to create the tables:

``python manage.py migrate``

You can now browse to https://yoursite/explorer/ and get exploring! It is highly recommended that you also configure Explorer to use a read-only database connection via the `EXPLORER_CONNECTION_NAME` setting.

There are a handful of features (snapshots, emailing queries) that rely on Celery and the dependencies in optional-requirements.txt. If you have Celery installed, set `EXPLORER_TASKS_ENABLED=True` in your settings.py to enable these features.

Dependencies
============

An effort has been made to keep the number of dependencies to a minimum.

*Python*

=========================================================== ======= ================
Name                                                        Version License
=========================================================== ======= ================
`sqlparse <https://github.com/andialbrecht/sqlparse/>`_     0.1.18  BS
`unicodecsv <https://github.com/jdunck/python-unicodecsv>`_ 0.14.1  BSD
=========================================================== ======= ================

- sqlparse is Used for SQL formatting

*Python - Optional Dependencies*

=========================================================== ======= ================
Name                                                        Version License
=========================================================== ======= ================
`celery <http://www.celeryproject.org/>`_                   3.1     BSD
`django-celery <http://www.celeryproject.org/>`_            3.1     BSD
`Factory Boy <https://github.com/rbarrois/factory_boy>`_    2.6.0   MIT
`xlsxwriter <http://xlsxwriter.readthedocs.io/>`_           0.8.5   BSD
`tinys3 <https://github.com/smore-inc/tinys3>`_             0.1.11  MIT
=========================================================== ======= ================

- Factory Boy is required for tests
- celery is required for the 'email' feature, and for snapshots
- tinys3 is required for snapshots
- xlsxwriter is required for Excel export (csv still works fine without it)

*JavaScript*

============================================================ ======== ================
Name                                                         Version  License
============================================================ ======== ================
`Twitter Boostrap <http://getbootstrap.com/>`_               3.3.6    MIT
`jQuery <http://jquery.com/>`_                               2.1.4    MIT
`jQuery Cookie <https://github.com/carhartl/jquery-cookie>`_ 1.4.1    MIT
`jQuery UI <https://jqueryui.com>`_                          1.11.4   MIT
`Underscore <http://underscorejs.org/>`_                     1.7.0    MIT
`Codemirror <http://codemirror.net/>`_                       5.15.2   MIT
`floatThead <http://mkoryak.github.io/floatThead/>`_         1.4.0    MIT
`list.js <http://listjs.com>`_                               1.2.0    MIT
`pivottable.js <http://nicolas.kruchten.com/pivottable/>`_   2.0.2    MIT
============================================================ ======== ================

- All all served from CDNJS except for jQuery UI, which uses a custom build, served locally.

pivottable.js relies on jQuery UI but only for the `Sortable` method.

## Reference:
https://github.com/groveco/django-sql-explorer
