***************************
django-webpresence-template
***************************

Personal project template for flexible web applications with a central web
presence or marketing component. Currently in early development. Delete this
README and replace it with you project's README.


========
Features
========

Incorporates Django Best Practices
Integrated CMS

========
Packages
========

These are some significant packages used.  For a full and current list, check 
the requirements folder.

----
Apps
----

* South
* Crispy Forms 
* Django CMS
* Zinnia

---------
Libraries
---------

-----
Tools
-----

=====
Setup
=====

-------------------
Working Environment
-------------------

create your project folder and set up a virtualenv directory. ::

    mkdir <directory_path>
    cd <directory_path>
    virtualenv .venv
    source .venv/bin/activate

-----------------
Installing Django
-----------------

Install django in your virtualenv.::

    pip install django


------------------
Creating a Project
------------------

To get started, start a new project with this as a template.::

    django-admin startproject --template=https://github.com/axelmagn/django-webpresence-template/archive/master.zip --extension=py,rst,html <project_name> <directory_path>

-----------------------
Installing Requirements
-----------------------

Install development packages.::

    pip install -r requirements/dev.txt

---------------------
Configure Environment
---------------------

Configuration relies on setting a number of variables in the environment.  Refer 
to the installation chapter in the docs.

=====
Usage
=====

-----------
Development
-----------

----------
Deployment
----------





