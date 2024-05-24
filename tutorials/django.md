# Django

### Django on the Tommy and Johnny servers uses Python 3.10. 

{% hint style="info" %} 
If you need to run Django on another version of Python, you'll need to get a [VPS](https://heliohost.org/vps/)
{% endhint %}

## About Django

Django is a web development framework designed specifically for Python. Like Ruby on Rails does for Ruby, Django aims to provide an MVC (Model-View-Controller) architecture for web application development as well as a large set of prebuilt libraries to simplify the development of common web app features. Django's modularity also allows easy scalability and enables the reuse of various code blocks, aligning to the DRY ("Don't Repeat Yourself") software development principle.

## Details

| Server | Django Version | Python Version | Python Path | Loader |
| :--- | :--- | :--- | :--- | :--- |
| Tommy | 4.1.1 | 3.10 | /usr/bin/python3.10 | WSGI |
| Johnny | 4.1.5 | 3.10 | /usr/bin/python3.10 | WSGI |

## Enabled

### WSGI

Using the WSGI loader for a shared hosting environment is ideal because it conserves memory and enhances security.

#### WSGI Uses Caching

{% hint style="warning" %}
Django changes can take **up to 2 hours** to appear consistently on your site because WSGI uses server side caching.

If you want site changes to take effect immediately, please refer to the options below.
{% endhint %}

#### What Caching Does

Multiple Apache processes are running on the server, and each time you refresh your site you are randomly assigned to one of these processes. If that particular process has already displayed your site, it shows the cached version of your code; otherwise, it shows the new code changes. This means that during the first 2 hours after a site change, you may intermittently see old or new content, depending on which process you get assigned to. This situation will resolve when Apache is restarted, which happens every 2 hours.

## Options to Work Around Caching

### 1. Request WSGI Control Access

A new feature currently in beta is the ability for users to restart their Django app themselves. 

To request this, please create a new post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide your **username**, **server name**, and the **domain name(s)** you want to be given WSGI Control Access for. (If you have 2 Django apps on 2 different domains, you need to request WSGI Control Access for each domain.)
<!-- TODO: Confirm if `dispatch.wsgi` is the correct file to edit -->
Once you have been given WSGI Control Access, you can edit your `dispatch.wsgi` to reload your Django app so new code changes load immediately. The edits to the file can be as simple as adding or removing a space or a blank line. As long as the file's `last modified date` changes it will discard the cache and reload your Django app.

Please let us know if you experience unexpected results with this new feature.

### 2. Use Local Development Environment

Another option to see code changes reflected immediately is to develop your Django app on your home computer and then host the production copy on the server.

### 3. VPS

You may prefer to explore one of our paid [VPS Plan](https://heliohost.org/vps/) options, depending on your requirements.

### Complete Django

We offer the complete, unadulterated Django package.

## Modules

You can see the modules that are currently installed on Python 3.10 used by Django:

### Johnny

* [Python 3.10](https://krydos2.heliohost.org/pyinfo/info3.10.py)

### Tommy

* [Python 3.10](https://krydos.heliohost.org/pyinfo/info3.10.py)

To request modules, please raise a request in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, your **server**, and **the module(s) you need** including any relevant **version numbers** for them.

## Disabled

### Shell Access

We don't offer shell (command line) access to our users. Many Django tutorials and installation instructions assume that users have command line access, which may make working with Python & Django more difficult. Most people tend to develop on their home computer and then upload to their web server, which almost negates the need for this feature. Furthermore, most configuration done through the command line can be done through other methods, such as FTP and manual file editing.

### WSGI Daemon Mode

There are two ways to configure Django to work with the mod_wsgi loader in Apache. You can either create a separate daemon for each Django process (daemon mode), or embed Django into the Apache daemon (embedded mode). While daemon mode tends to be the standard among Django admins because of the increased control it offers, we use embedded mode because it can be setup on a per-user basis without very much root-level configuration. Embedded mode is slightly harder to get working (see directions below), and might break compatibility with some Django tutorials. In most cases it should not be a problem.

## Getting started with Django 4.1

The official Django 4.1 documentation [is available here](https://docs.djangoproject.com/en/4.1). The following guide has been adapted from [this post](https://www.helionet.org/index/topic/27585-django-on-tommy/?p=126077). It's suggested to follow the [introduction tutorial](https://docs.djangoproject.com/en/4.1/intro/tutorial01/) to start off with Django: another suggestion is to try and test the package locally before uploading it online, since shell access (sometimes useful for debugging) is not provided on HelioHost.

Django 4.1 and later (available on Tommy and Johnny) comes with a new structure to manage its web-apps, so we're going to look in details how to set it up on a shared hosting like HelioHost. This small tutorial has been thought for Linux users, but Windows users should work it out easily.

Let's start by creating an empty "dumb" application to play with: refer to the official documentation for instructions on how to setup Django on a personal computer (we suggest using virtualenv, to differentiate each Django installation for each project).

**Conventions:** All the following commands don't need root access to be executed, but the shell commands are preceded by a `$` (dollar sign) to differentiate them from the output.  
The python executable name used on the local computer is python3 (as on a Fedora OS), but this could change according with the distribution used (e.g. Ubuntu could name it `python3.6`): change it accordingly to your executable name.

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
├── hello
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── settings.cpython-310.pyc
│   │   └── urls.cpython-310.pyc
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py

2 directories, 10 files
```

Run the included testing server:

```text
$ python3 manage.py runserver 0.0.0.0:8000
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
May 24, 2024 - 22:44:26
Django version 4.1, using settings 'hello.settings'
Starting development server at http://0.0.0.0:8000/
Quit the server with CONTROL-C.
```

Now you can point your browser to the address stated ([http://127.0.0.1:8000](http://127.0.0.1:8000/)), and you should see the Django `The install worked successfully! Congratulations!` debug message.

![](../.gitbook/assets/django-install-success.png)

Let's set the project up to work on HelioHost; we need to rename and link back the `wsgi.py` file.

```text
$ cd hello/
$ mv wsgi.py dispatch.wsgi
```

(Windows users should skip the following step and manually copy `dispatch.wsgi` to `wsgi.py` each time they overwrite `dispatch.wsgi`):

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

This instructs Apache to redirect all the requests (except those requesting something from `media/` or `admin_media/`) to the dispatcher file.

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

So your website (say `djangoprogrammer.heliohost.org`, every custom domain you set up like `djangoprogrammer.com` and every subdomain such as `www`) can be served by your application.

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

The hello will be created on your working directory. Copy the content of that folder (`hello` folder and `manage.py` file) to your `public_html` folder.

Eventually you can point your browser to your website address(es) and you should see your Django application being online!

## References

* The original discussion from which the tutorial for Django 1.10 came out - [http://www.helionet.org/index/topic/27585-django-on-tommy/](http://www.helionet.org/index/topic/27585-django-on-tommy/).
* GitHub repository for cookiecutter recipe for HelioHost at [https://github.com/rahul-gj/cookiecutter-helio](https://github.com/rahul-gj/cookiecutter-helio).

