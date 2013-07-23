Install
~~~~~~~

This is where you write how to get a new laptop to run this project.


Configuration
=============

In keeping with best practices laid out at `The Twelve-Factor App`_,
configurations that could vary between machine or deployment environment are
retrieved from environment variables.  It is therefore necessary to set some
environment variables either manually or using script outside of version 
control. Depending on your platform, some of these variables may already be
set. 

These variables are a great thing to export in your virtualenv activate
script. My preferred method is to create a separate file in your virtualenv at
bin/environ::

    # <venv>/bin/environ
    export DATABASE_URL=...
    ...

then source that file at the bottom of the activate script with::

    # <venv>/bin/activate
    ...
    source "$VIRTUAL_ENV/bin/environ"

DATABASE_URL
------------

Tells your app what database to consume with package dj-database-url. Maps to
``settings.DATABASES['default']``.

::

    export DATABASE_URL=postgres://<dbuser>:<dbpassword>@<host>/<db_name>
    
If you are deploying to heroku, this variable will already be set. Heroku will
also expect your app to use Postgres as your DB, as will this template.

DJANGO_DEBUG
------------

Maps to ``settings.DEBUG``. Defaults to False, but it's still good to set for 
clarity.::

    export DJANGO_DEBUG=<1|True|true>



.. `The Twelve Factor App`: http://www.12factor.net/

