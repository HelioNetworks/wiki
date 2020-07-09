# Django

Django is a web development framework designed specifically for Python. Like Ruby on Rails does for Ruby, Django aims to provide a Model-View-Controller framework for web application development as well as a large set of prebuilt libraries to simplify the development of common web app features. Django's modularity also allows easy scalability and enables the reuse of various code blocks, under the policy of "Don't Repeat Yourself".

### Details

| Server | Django Version | Python Version | Python Path | Loader |
| :--- | :--- | :--- | :--- | :--- |
| Tommy | 2.1.13 | 3.7 | /usr/bin/python3.7 | WSGI |
| Ricky | 1.11.4 | 2.7 | /usr/bin/python2.7 | WSGI |
| Johnny | 2.1.13 | 3.7 | /usr/bin/python3.7 | WSGI |

### Enabled

#### WSGI

Using the WSGI loader for a shared hosting environment is ideal because it conserves memory and enhances security.

#### Complete Django

We offer the complete, unadulterated Django package.

#### MySQL

Our Python installation includes the MySQL extension for interfacing with the MySQL database engine.

#### PostgreSQL

Our Python installation includes the PostgreSQL extension for interfacing with the PostgreSQL database engine.

#### SQLite

Our Python installation includes the SQLite extension for interfacing with the SQLite database engine.

#### Extensive Prebuilt Libraries

If you need any additional libraries installed be sure to ask at [https://www.helionet.org](https://www.helionet.org/index/).

### Disabled

#### Shell Access

We don't offer shell \(command line\) access to our users. Many Django tutorials and installation instructions assume that users have command line access, which may make working with Python & Django more difficult. Most people tend to develop on their home computer and then upload to their web server, which almost negates the need for this feature. Furthermore, most configuration done through the command line can be done through other methods, such as FTP and manual file editing.

#### WSGI Daemon Mode

There are two ways to configure Django to work with the mod\_wsgi loader in Apache. You can either create a separate daemon for each Django process \(daemon mode\), or embed Django into the Apache daemon \(embedded mode\). While daemon mode tends to be the standard among Django admins because of the increased control it offers, we use embedded mode because it can be setup on a per-user basis without very much root-level configuration. Embedded mode is slightly harder to get working \(see directions below\), and might break compatibility with some Django tutorials. In most cases it should not be a problem.

### Getting started with Django 1.11

The official Django 1.11 documentation [is available here](https://docs.djangoproject.com/en/1.11/). The following guide is based on [this post](https://www.helionet.org/index/topic/27585-django-on-tommy/?p=126077). It's suggested to follow the [introduction tutorial](https://docs.djangoproject.com/en/1.11/intro/tutorial01/) to start off with Django: another suggestion is to try and test the package locally before uploading it online, since shell access \(sometimes useful for debugging\) is not provided on HelioHost.

Django 1.10 and later \(available on Tommy and Johnny\) comes with a new structure to manage its web-apps, so we're going to look in details how to set it up on a shared hosting like HelioHost. This small tutorial has been thought for Linux users, but Windows users should work it out easily.

Let's start by creating an empty "dumb" application to play with: refer to the official documentation for instructions on how to setup Django on a personal computer \(we suggest using virtualenv, to differentiate each Django installation for each project\).

**Conventions:** All the following commands don't need root access to be executed, but the shell commands are preceded by a `$` \(dollar sign\) to differentiate them from the output.  
The python executable name used on the local computer is python3 \(as on a Fedora OS\), but this could change according with the distribution used \(e.g. Ubuntu could name it `python3.6`\): change it accordingly to your executable name.

On your local computer, open a terminal, create a new project and perform the minimal configuration:

```text
$ django-admin startproject hello
$ cd hello/ && python3 manage.py migrate
```

This should return a directory structure like this:

```text
$ tree ../hello/
../hello/
├── db.sqlite3
├── hello/
│   ├── __init__.py
│   ├── __pycache__/
│   │   ├── ...
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py

2 directories, 10 files
```

Run the included testing server:

```text
$ python3 manage.py runserver 0.0.0.0:8000
Performing system checks...

System check identified no issues (0 silenced).
March 20, 2017 - 16:42:48
Django version 1.10.6, using settings 'hello.settings'
Starting development server at http://0.0.0.0:8000/
Quit the server with CONTROL-C.
...
```

Now you can point your browser to the address stated \([http://127.0.0.1:8000](http://127.0.0.1:8000/)\), and you should see the Django `hello world` debug message.

Let's set the project up to work on HelioHost; we need to rename and link back the `wsgi.py` file.

```text
$ cd hello/
$ mv wsgi.py dispatch.wsgi
```

\(Windows users should skip the following step and manually copy `dispatch.wsgi` to `wsgi.py` each time they overwrite `dispatch.wsgi`\):

```text
$ ln -s dispatch.wsgi wsgi.py
```

In this way, you can go on doing any edit you need on `wsgi.py`, since it's just a symbolic link to `dispatch.wsgi`, which is a configuration file needed to make your Django web app work on HelioHost.

Then create a `.htaccess` file in `/home/username/public_html/hello/` containing the instructions for the Apache web server to redirect HTTP requests to your Django app.

The content should be:

```text
RewriteEngine On
RewriteBase /
RewriteRule ^(media/.*)$ - [L]
RewriteRule ^(admin_media/.*)$ - [L]
RewriteRule ^(hello/dispatch\.wsgi/.*)$ - [L]
RewriteRule ^(.*)$ hello/hello/dispatch.wsgi/$1 [QSA,PT,L]
```

This instructs Apache to redirect all the requests \(except those requesting something from `media/` or `admin_media/`\) to the dispatcher file.

We are not done yet: we need to tell the dispatcher file `dispatch.wsgi` how to load your Django settings; change it from:

```text
import os

from django.core.wsgi import get_wsgi_application

os.environ.setdefault("DJANGO_SETTINGS_MODULE", "hello.settings")

application = get_wsgi_application()
```

To something like:

```text
import os, sys

# edit your username below
sys.path.append("/home/username_on_heliohost/public_html/hello")

from django.core.wsgi import get_wsgi_application

os.environ['DJANGO_SETTINGS_MODULE'] = 'hello.settings'

application = get_wsgi_application()
```

Change `username_on_heliohost` to the HelioHost username used on the web server.  
In order to allow the web server to serve your Django app, you need to add the web server address in the app settings. Change `hello/settings.py` and change:

```text
ALLOWED_HOSTS = []
```

to

```text
ALLOWED_HOSTS = ["*"]
```

So your website \(say `djangoprogrammer.heliohost.org`, every custom domain you set up like `djangoprogrammer.com` and every subdomain such as `www`\) can be served by your application.

Now upload the content of the `hello/` folder to your `public_html/` folder, using whichever method you prefer, so the final content on the HelioHost web server should be something like:

```text
$ tree home/
home/
└── username_on_heliohost/
    └── public_html/
        ├── db.sqlite3
        ├── manage.py
        └── hello/
            ├── .htaccess
            ├── dispatch.wsgi
            ├── __init__.py
            ├── __pycache__/
            │   ├── ...
            ├── settings.py
            ├── urls.py
            └── wsgi.py -> dispatch.wsgi
```

```text
4 directories, 10 files
```

If you want ready made template, on you computer having python 3:

First install cookiecutter:

```text
$ pip install cookiecutter
```

If you are using git:

```text
$ cookiecutter https://github.com/rahul-gj/cookiecutter-helio.git
```

If you are not using git then download `cookiecutter-helio-master.zip` file from [https://github.com/rahul-gj/cookiecutter-helio](https://github.com/rahul-gj/cookiecutter-helio):

```text
$ cookiecutter path/to/cookiecutter-helio-master.zip
```

 The shell will then asks few questions. Answer them:

```text
$ project_name [mysite]: hello--> Choose any name
$ helio_user [user_name]: yourusername    --> Type your username on heliohost.org
```

The hello will be created on your working directory. Copy the content of that folder \(`hello` folder and `manage.py` file\) to your `public_html` folder.

Eventually you can point your browser to your website address\(es\) and you should see your Django application being online!

### References

* The original discussion from which the tutorial for Django 1.10 came out - [http://www.helionet.org/index/topic/27585-django-on-tommy/](http://www.helionet.org/index/topic/27585-django-on-tommy/).
* GitHub repository for cookiecutter recipe for HelioHost at [https://github.com/rahul-gj/cookiecutter-helio](https://github.com/rahul-gj/cookiecutter-helio).

