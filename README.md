django-crowd
============

Simple Attlasian CROWD authentication backend for Django

Configuration:
==============

Put a CROWD configuration in your settings.py:

CROWD = {

    'url': 'http://your.crowd.url:port/crowd/rest',         # your CROWD rest API url

    'app_name': 'your-registered-crowd-application-name',   # appname, registered with CROWD

    'password': 'application-password',                     # correct password for provided appname

    'superuser': True,                                      # if set makes CROWD-authorized users superusers;
                                                            # BE CAREFUL WITH THIS PARAMETER!
}

Also add 'crowd.CrowdBackend' in your AUTHENTICATION_BACKENDS settings list.
Better to put it last for minimal collision risk:

AUTHENTICATION_BACKENDS = (

    # ...

    'django.contrib.auth.backends.ModelBackend',

    'django_crowd.CrowdBackend'
)

Credits:
========

Originally written for Django v1.3 by Konstantin J. Volkov <konstantin-j-volkov@yandex.ru> at 12.07.2012

Refactored, put together and tested with Django v1.4 by Grigoriy Beziuk <gbezyuk@gmail.com> at 27.08.2012
