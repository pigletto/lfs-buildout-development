What is it?
===========

This is the development buildout script for LFS with experimental (work in progress!) content translation support.

It will create a complete developement evironment for LFS using branches of lfs, lfs-theme that are modified to support
content translations. By default this project is configured to use english as default language and german and polish as
additional languages.

The main difference beetween this version and original lfs-buildout-development is that this project uses
django-modeltranslation and django-localeurl for translation support.

LFS is an online shop based on Python, Django and jQuery.

How to use it?
==============

1. Check it out from bitbucket
    
    $ hg clone https://bitbucket.org/diefenbach/lfs-buildout-development

2. Change to the directory

    $ cd lfs-buildout-development
    
3. Bootstrap buildout

    $ python bootstrap.py
    
4. Run buildout

    $ bin/buildout -v
    
5. Enter your database settings into lfs_project/settings.py

6. Sync your database

    $ bin/django syncdb

7. Run translation migration scripts (it will create fields for translated versions of content -
see django-modeltranslation for details)

    $ bin/django sync_translation_fields
    $ bin/django update_translation_fields

8. Initialize LFS

    $ bin/django lfs_init

9. Start server

    $ bin/django runserver
    
10. Browse to LFS

    http://localhost:8000

11. or for German version:

    http://localhost:8000/de/

12. or for Polish version:

    http://localhost:8000/pl/

    
More Information
================

* `Official page <http://www.getlfs.com/>`_
* `Documentation on PyPI <http://packages.python.org/django-lfs/index.html>`_
* `Releases on PyPI <http://pypi.python.org/pypi/django-lfs>`_
* `Source code on bitbucket.org <http://bitbucket.org/diefenbach/django-lfs>`_
* `Google Group <http://groups.google.com/group/django-lfs>`_
* `lfsproject on Twitter <http://twitter.com/lfsproject>`_
* `IRC <irc://irc.freenode.net/django-lfs>`_
