Heroku
======

Craig Kirstens

"    " as a service
* Software
* Infrastructure
* Platform

Software as a Service is for users: New features, transparent upgrades, etc..

Infrastructure is for ops people: On Demand machines

Platform as a Service: For developers, Transparent updates, don't think about servers

Heroku works with:
* Ruby
* Python
* Java
* Node.js
* etc...

Demo on 
=======

Lightweight Todo app: simple django application.

Heroku command line tool: 
    heroku create -s cedar
    git push heroku master
    heroku open
    heroku run python app/manage.py syncdb
    heroku open

requirements.txt contains the modules versions required for the application.  Heroku knows to compile these into a "slug" with your code (basically a tarball).

Scaling Heroku
--------------
    heroku scale web=32
    heroku ps
    heroku log --tail 

Heroku
======

Run the processes you tell us to run

pip/virtualenv

Heroku uses virtualenv/pip to do it's installs

Procfile
--------
    web: run python app/manage.py runserver 0.0.0.0:$PORT

Dyno
====
"Worker Process" of any sort.  You can scale web, celery processes, etc.

You can run batches, you can run syncdb, bash, etc...

Each "heroku run ..." runs with a fresh copy of the tarball.

Don't use SQLite in production, because you don't have a shared file. (duh)

Q&A
===
Do you have autoscaling?
> Nope, there are third party tools, but none of them are "quite baked" so Heroku isn't looking at doing it in house yet.

Can you run multiple processes per Dyno? 
> Yeah, but it's not easy.  Don't worry about it (unless you absolutely must)

Additional Services
===================
* Memcache
* Redis
* Mongo
* Email
* App Performance
* Logging

Provided by third party groups, but handled pretty quickly and easily. 

     heroku addons:add memcache
     heroku addons:add postgresql
     heroku config

     heroku config:add MY_OTHER_DB=someurlhere

example.py
----------
     MY_OTHER_DB=os.environ.get('MY_OTHER_DB')

Customer Notebook
=================
Danny Greenfeld

http://consumernotebook.com

http://bit.ly/django-books-l
http://bit.ly/wedding-dress-options

Universal product system, bookmarklet, etc..

What did they need?
-------------------
* Python
* Django
* Datamodeling
* Page Layout
* JavaScript
* Sys Admin
* Community Management
* User Experience
* Marketing
* Vendor Contacts
* Business Stuff
* Legal Stuff

Iteration
=========

Design was built on top of functionality, functionality needed to be flexible, Backend needed to be easy to deploy, no fighting with the system, it just needed to work. 

Devops doesn't make system administration easier, you just spend more time developing scripts for Chef and Puppet.  Some people love sys admin, but their skills are better used elsewhere. 

Several PaaS setups were evaluated.  Heroku was not just a couple of folks in a garage.  SalesForce isn't going anywhere.  

What does PaaS mean?  It means that "Sys Admin" work pretty much vanishes.

    en_project
    docs
    .gitignore
    .slugignore
    Makefile



