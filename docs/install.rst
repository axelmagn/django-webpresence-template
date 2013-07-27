Install
~~~~~~~

This is where you write how to get a new laptop to run this project.


Configuration
=============

In keeping with best practices laid out at `The Twelve-Factor App`,
configurations that could vary between machine or deployment environment are
retrieved from environment variables.  It is therefore necessary to set some
environment variables either manually or using script outside of version
control. Depending on your platform, some of these variables may already be
set. Unless otherwise specified, these map to the settings variable of the same 
name.

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
``settings.DATABASES['default']``.::

    export DATABASE_URL=postgres://<dbuser>:<dbpassword>@<host>/<db_name>
 
If you are deploying to heroku, this variable will already be set. Heroku will
also expect your app to use Postgres as your DB, as will this template.

ADMIN_NAME
----------

Maps to ``settings.ADMINS[0][0]``.::
    
    export ADMIN_NAME="Your Name"

ADMIN_EMAIL
-----------

Maps to ``settings.ADMINS[0][1]``.::

    export ADMIN_EMAIL=your_email@example.com

SECRET_KEY
----------

Keep it secret.  Keep it safe.  Preferably some random-ass string. I like to
generate it with::

    echo "export SECRET_KEY=`date | sha256sum | base64 | head -c 64`" >> environ_file

ALLOWED_HOSTS
-------------
Maps to ``settings.ALLOWED_HOSTS`` as a list.  Separate multiple host names 
with commas, or hard code it into the settings file.::

    export ALLOWED_HOSTS=example.com,foo.bar

DEBUG (OPTIONAL)
----------------

Defaults to False, but it's still good to set for clarity.::

    export DEBUG=<1|True|true>

EMAIL_HOST (OPTIONAL)
---------------------

Defaults to ``smtp.gmail.com``

EMAIL_HOST_USER (OPTIONAL)
--------------------------

Defaults to an empty string.::

    export EMAIL_HOST_USER=your_email@gmail.com


EMAIL_HOST_PASSWORD (OPTIONAL)
------------------------------

Defaults to an empty string.




.. `The Twelve Factor App`: http://www.12factor.net/

