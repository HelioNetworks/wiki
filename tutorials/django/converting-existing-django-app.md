# Converting an Existing Django App to work on HelioHost

## About Django

Django is a web development framework designed specifically for Python. As Ruby on Rails does for Ruby, Django aims to provide an MVC (Model-View-Controller) architecture for web application development as well as a large set of prebuilt libraries to simplify the development of common web app features. Django's modularity also allows easy scalability and enables the reuse of various code blocks, aligning to the DRY ("Don't Repeat Yourself") software development principle.

## Johnny server

{% hint style="info" %} 
If you need to run Django on another version of Python, you'll need to get a [VPS](https://heliohost.org/vps/).
{% endhint %}
<!-- The column with the link to view installed modules should stay as far left as possible, to prevent an overlapping div from the rightside nav menu making it difficult to mouseover and click on in the live Wiki. -->
| Server | Django Version | Python Version | Python Modules Installed                                 | Python Path         | Loader | 
| :----: | :------------: | :------------: | :------------------------------------------------------: | :-----------------: | :----: | 
| Johnny | 5.0.7          | 3.12           | [View](https://krydos2.heliohost.org/pyinfo/info3.12.py) | /usr/bin/python3.12 | WSGI   | 

## Tommy server

{% hint style="info" %} 
If you need to run Django on another version of Python, you'll need to get a [VPS](https://heliohost.org/vps/).
{% endhint %}
<!-- The column with the link to view installed modules should stay as far left as possible, to prevent an overlapping div from the rightside nav menu making it difficult to mouseover and click on in the live Wiki. -->
| Server | Django Version | Python Version | Python Modules Installed                                 | Python Path         | Loader | 
| :----: | :------------: | :------------: | :------------------------------------------------------: | :-----------------: | :----: | 
| Tommy  | 5.0.7          | 3.12           | [View](https://krydos1.heliohost.org/pyinfo/info3.12.py) | /usr/bin/python3.12 | WSGI   | 

## Enabled

### WSGI

Using the WSGI loader for a shared hosting environment is ideal because it conserves memory and enhances security.

{% hint style="warning" %}
Django changes can take **up to 2 hours** to appear consistently on your site because [WSGI uses server side caching](#wsgi-uses-server-side-caching).

If you want site changes to take effect immediately, we offer a few [options to work around caching](#options-to-work-around-caching).
{% endhint %}

### Complete Django

We offer the complete, unadulterated Django package, including extensions to interface with [MySQL](../../management/mysql.md), [PostgreSQL](../../features/postgresql.md), and [SQLite](../../features/sqlite.md) database engines.

### Additional Libraries

View the [Python modules installed on Johnny](https://krydos2.heliohost.org/pyinfo/info3.12.py).  
View the [Python modules installed on Tommy](https://krydos1.heliohost.org/pyinfo/info3.12.py).

To request additional libraries, please raise a request in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, your **server**, and **the libraries you need** including any relevant **version numbers** for them.

## Disabled

### Shell Access

We don't offer shell (command line) access to our users. Many Django tutorials and installation instructions assume that users have command line access, which may make working with Python & Django more difficult. Most people tend to develop on their home computer and then upload to their web server, which almost negates the need for this feature. Furthermore, most configuration done through the command line can be done through other methods, such as FTP and manual file editing.

### WSGI Daemon Mode

There are two ways to configure Django to work with the mod_wsgi loader in Apache. You can either create a separate daemon for each Django process (daemon mode) or embed Django into the Apache daemon (embedded mode). While daemon mode tends to be the standard among Django admins because of the increased control it offers, we use embedded mode because it can be set up on a per-user basis without very much root-level configuration. Embedded mode is slightly harder to get working (see directions below), and might break compatibility with some Django tutorials. In most cases, it should not be a problem.

## Converting an Existing Django App to work on HelioHost

This tutorial will guide you through using the command line on your development system to convert an existing Django app for hosting on HelioHost.

If you prefer not to use the command line, our brief [Django on HelioHost](django-on-heliohost.md) tutorial may better suit your needs. 

We recommend referring to the [official Django documentation](https://docs.djangoproject.com/) and following the introduction tutorial relevant to the Django version you are using. Please note the Django versions available are different on the [Johnny](#django-on-the-johnny-server-uses-python-312) and [Tommy](#django-on-the-tommy-server-uses-python-310) servers. We also suggest using `virtualenv` to differentiate each Django installation for each project. The below tutorial has been designed for Linux users, but Windows users should work it out easily. 

**Conventions:** The following commands don't need root access to be executed. Shell commands are preceded by a `$` (dollar sign) to differentiate them from the output.  
The Python executable name used on the local computer is `python3`, but this can vary depending on the distribution used, so change it as needed to match your system requirements. 

### 1. Create a new project called `djangotest`

On your local computer, open a terminal, create a new project and perform the minimal configuration:

```text
$ django-admin startproject djangotest
$ cd djangotest/ && python3 manage.py migrate
```

### 2. Verify Project Structure

The below directory structure, with a `djangotest` folder nested inside another `djangotest` folder, is standard for a Django project. Please note that you cannot name the project folder `django`, it will not work. This is why the name `djangotest` has been used for this tutorial.

Make sure that your directory structure and files look like this:

```text
$ tree ../djangotest/

../djangotest/
├── db.sqlite3
├── djangotest
│   ├── __init__.py
│   ├── __pycache__/
│   │   ├── ...
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py

2 directories, 10 files
```

### 3. Run the Test Server

Inside the first (outer) `djangotest` folder, start the testing server.

```text
$ python3 manage.py runserver 0.0.0.0:8000

Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
May 31, 2024 - 18:12:55
Django version 4.1, using settings 'djangotest.settings'
Starting development server at http://0.0.0.0:8000/
Quit the server with CONTROL-C.
```

### 4. Open Test Server in Browser

By using the test server, you can develop the app on your local computer and changes you make will take effect immediately.  

Point your web browser to [http://127.0.0.1:8000](http://127.0.0.1:8000/) and you should see a message confirming the installation worked successfully:

![](../../.gitbook/assets/django-install-success.png)

### 5. Configuring the Project for Deployment

{% hint style="warning" %}
Django changes can take **up to 2 hours** to appear consistently on your site because [WSGI uses server side caching](#wsgi-uses-server-side-caching).

If you want site changes to take effect immediately, we offer a few [options to work around caching](#options-to-work-around-caching).
{% endhint %}

### 6. Rename the `wsgi.py` file to `dispatch.wsgi`

To prepare the project for deployment, rename the `wsgi.py` file to `dispatch.wsgi`. Both files are inside the second (inner) `djangotest` folder.

```text
$ mv djangotest/wsgi.py djangotest/dispatch.wsgi
```

### 7. Create an `.htaccess` file 

Inside the first (outer) `djangotest` folder, create an `.htaccess` file with these contents:

```text
Options +ExecCGI
RewriteEngine On
RewriteBase /
RewriteRule ^(media/.*)$ - [L]
RewriteRule ^(admin_media/.*)$ - [L]
RewriteRule ^(djangotest/dispatch\.wsgi/.*)$ - [L]
RewriteRule ^(.*)$ djangotest/djangotest/dispatch.wsgi/$1 [QSA,PT,L]
```

This instructs Apache to redirect all the requests (except those requesting something from `media/` or `admin_media/`) to the dispatcher file.

### 8. Edit the `dispatch.wsgi` file

Inside the second (inner) `djangotest` folder, edit the dispatcher file `dispatch.wsgi` to instruct it how to load your Django settings. Change it from:

```text
import os

from django.core.wsgi import get_wsgi_application

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'djangotest.settings')

application = get_wsgi_application()
```

To the below:

```text
import os, sys

# edit your path below
sys.path.append("/home/domain.helioho.st/httpdocs/djangotest")

from django.core.wsgi import get_wsgi_application
os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'djangotest.settings')
application = get_wsgi_application()
```

#### Make sure to edit your path

If you were transferred from the old cPanel, your main domain will be parked on the `public_html` directory.

If you created a new account on Plesk, your directory will be `httpdocs`.

### 9. Edit the `urls.py` file

Inside the second (inner) `djangotest` folder, edit the `urls.py` file. Change it from:

```text
from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('admin/', admin.site.urls),
]
```

To the below:

```text
from django.contrib import admin
from django.urls import path

urlpatterns = [
#    path('admin/', admin.site.urls),
]
```

Commenting out the path to the admin interface is done for security reasons, to prevent unauthorized access to the admin panel in a production environment.

### 10. Edit the `settings.py` file

Inside the second (inner) `djangotest` folder, edit the `settings.py` file. 

Adding the web server address to the app settings will allow the web server to serve your Django app. Change it from: 

```text
ALLOWED_HOSTS = []
```

To the below:

```text
ALLOWED_HOSTS = ["*"]
```

This will ensure that your website (such as `domain.heliohost.us`) can serve your application from any custom domains you have (such as `domain.com`) as well as every subdomain (such as `www`).

### 11. Upload Your Project to HelioHost

Upload the entire first (outer) `djangotest` folder to your main domain. Make sure that your directory structure and files look like this:

```text
home/
└── domain/
    └── httpdocs/
        ├── .htaccess
        ├── db.sqlite3
        ├── manage.py
        └── djangotest/
            └── djangotest/
                ├── __init__.py
                ├── asgi.py
                ├── dispatch.wsgi
                ├── settings.py
                ├── urls.py
                └── __pycache__/ 
                    ├── ...
``` 

### 12. Visit Your Deployed Site

{% hint style="warning" %}
Django changes can take **up to 2 hours** to appear consistently on your site because [WSGI uses server side caching](#wsgi-uses-server-side-caching).

If you want site changes to take effect immediately, we offer a few [options to work around caching](#options-to-work-around-caching).
{% endhint %}

In your web browser, navigate to `domain.helioho.st/djangotest`

If you did everything right it should look like this: 

![](../../.gitbook/assets/django-install-success.png)

## WSGI Uses Server Side Caching

### What WSGI Server Side Caching Does

Multiple Apache processes are running on the server, and each time you refresh your site you are randomly assigned to one of these processes. If that particular process has already displayed your site, it shows the cached version of your code; otherwise, it shows the new code changes. This means that during the first 2 hours after a site change, you may intermittently see old or new content, depending on which process you get assigned to. This situation will resolve when Apache is restarted, which happens every 2 hours.

## Options to Work Around Caching

### 1. Request WSGI Control Access

A new feature currently in beta is the ability for users to restart their Django app themselves. 

To request this, please create a new post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide your **username**, **server name**, and the **domain name(s)** you want to be given WSGI Control Access for. (If you have 2 Django apps on 2 different domains, you need to request WSGI Control Access for each domain.)

Once you have been given WSGI Control Access, you can edit your `dispatch.wsgi` to reload your Django app so new code changes load immediately. The edits to the file can be as simple as adding or removing a space or a blank line. As long as the file's `last modified date` changes it will discard the cache and reload your Django app.

Please let us know if you experience unexpected results with this new feature.

#### Account Resets Remove WSGI Control Access

{% hint style="info" %}
If you [request an account reset](../../faq.md#how-do-i-reset-my-hosting-account-to-start-fresh) you will need to re-request WSGI Control Access after the reset has been completed. By default, account resets will disable WSGI Control Access.
{% endhint %}

### 2. Use Local Development Environment

Another option to see code changes reflected immediately is to develop your Django app on your home computer and then host the production copy on the server.

### 3. VPS

You may prefer to explore one of our paid [VPS Plan](https://heliohost.org/vps/) options, depending on your requirements.

## References

* This tutorial is adapted from [this post](https://www.helionet.org/index/topic/27585-django-on-tommy/?p=126077) on the HelioNet forum.
* A ready-made template using an older Django version (1.11) is available at [https://github.com/rahul-gj/cookiecutter-helio](https://github.com/rahul-gj/cookiecutter-helio).