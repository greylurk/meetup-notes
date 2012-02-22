Deploying Django
================
or: just use Heroku

@btriley

Deploying is confusing
======================
* gunicorn vs uwsgi
* nginx vs apache
* ? vs ?

Two layers
========== 
 * Web
 * Django

The Web Layer
=============

nginx is an HTTP and reverse proxy server.  Serves static media files, proxies requests for dynamic content to an application server such as Django (via wsgi).  Nginx is very lightweight.

Nginx conf
==========
    server {
      listen 80 default;
      server_name example.com;
    
      location /static/ {
        root /path/to/project;
      }
    
      location / {
        proxy_pass http://127.0.0.1:8000;
      }
    }

Psuedo-json configurations are a little easier to read than the psuedo-xml that Apache uses.  Basic configuration is pretty simple, and you don't have the complexity of modules in Apache.  It has built in caching, which is pretty useful.

Wsgi server
===========
Gunicorn (Green Unicorn) is python built, pretty easy to use, just use Pip to install.  Once it's installed, "./manage.py run_gunicorn"

Pronounced "Gun icorn"

Upstart
=======
Comes with Ubuntu

Automates startup/shutdown of processes.

Use to manage your gunicorn service

    service gunicorn [start|stop|restart]

sample /etc/init/gunicorn.conf
------------------------------

    description "Gunicorn for my Django application"
    
    start on runlevel [2345]
    stop on runlevel [!2345]
    kill timeout 5

    env PROJECT_ROOT="/opt/my_django_app"

    script
	exec python $PROJECT_ROOT/portal/manage.py run_gunicorn --settings=settings.production --preload -w 16 --log-level debug --log-file /var/log/my_django_app/gunicorn.log -p /var/run/gunicorn.pid
    end script

Build Automation
================

Set up Fabric for automated deployment.  Fabric runs remote shell commands via ssh.

    fab deploy

Q&A
===

Static files, where do you put them?  On the Nginx server or on the Django server?  
> It depends on your setup, potentially on CDN,  

How do you physically move files around with Fabric? 
> Use SCP or rsync

How do you manage rolling back schema/data migrations with Fabric?
> You be careful.  
> South handles some of it, but you may have to hand-code some of the SQL, 
> Run tests at each deployment, 

The "Double the cores" rule of thumbs seems a little low on the number of worker processes for a blocking handler.  
> Yeah, but it's a good place to start. 

What about memory usage?
> Do testing, and figure out what's right for your app

Should Gunicorn be used without Nginx? 
> Probably not.  It's vulnerable to the "Slow Loris" attack.

Rackspace vs VPS...  Is Gunicorn/Nginx workable on a VPS?
> Sure, it really depends on your app. 


