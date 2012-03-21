Django Templating
=================

Christine Cheung
http://www.xtine.net
@plaidxtine

PyCon talk

Front End Developer
Santa Monica Startup

President of Pyladies

Speaker at DjangoCon and PyCon

Intro to templating
-------------------

 - How to use built in tags
 - Extending templates
 - What's coming in Django 1.4

Templating 101
--------------

 - This is the end user experience
 - Balance between power and elegance

Helpful hints
-------------

 - django-debug-toolbar

 - Print out tag/filter reference guide

Folder Structure
----------------

Keep them all together.

Think PEP8 coding convention
- consistent spacing
- {%load%} all template tags up at the top
- try {#comments#} rather than <!-- comments -->
  - also use {% comment %} {% endcomment %}

General structure
-----------------

Start with base.html
  - Content block
  - title block
  - meta_tags, robots
  - extra_head
  - content
  - extra_js

End Blocks always
  - {% block title %} .............. {% endblock title %}

Can't repeat blocks
  - Custom Template Tags
  - context processor
  - include

Don't over-block

Includes are good
... but don't overuse them (include an include from an include )

Variables tend to be objects passed from a view.  You can modify them with filters ( {{ variable|lower }} ), 
Loop through variables using tags. 

Security isn't often a major concern, but there is a safe or {% autoescape %}
ALWAYS SANITIZE DATA YOU'RE USING SAFE ON!

{% url %} points to other pages defined in urls.py

Use {{STATIC_URL}} when refering to static items

For forms, use plugins 
- django-floppyforms
- django-crispy-forms

as_ul makes more sense than p or br

Custom tags and filters
-----------------------

templatetags/
  demo_utils.py

{% load demo_utils %}

Filters are just functions to operate on the variable.  They can accept other arguments as well.

Making a custom tag
-------------------

Tags can do just about anything.  They're extremly flexible

Simple tag library is pretty simple.  

Full tags use nodes, classes, and kind of crasy shite.

 - django-classy-tags
 - django-templatetag-sugar

Do not:
  - Run logic.  Defeats the purpose of a templating language. 

Template loading logic
----------------------

TEMPLATE_LOADERS setting

Replacing Django templating language
------------------------------------

Jinja2, Mako, Cheetah,

Why?
  - Familiarity with other template engines
  - Speed
  - Different logic control and handling
Why not?
  - Frankenstine projects

Speedups
--------

  - Cache template loaders
  - django-template-preprocessor
    - "compiles" django templates
  - django-pancake
    - "flattens" django templates

New in Django 1.4
-----------------

  startapp/startproject accepts a base.html tempalte

elseif

