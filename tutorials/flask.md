# Flask

### Flask on the Tommy and Johnny servers uses Python 3.10. 

{% hint style="info" %} 
If you need to run Flask on another version of Python, you'll need to get a [VPS](https://heliohost.org/vps/)
{% endhint %}

## About Flask

Flask is a Python web framework built with a small core and easy-to-extend philosophy.  
Read more: [Full Stack Python](https://www.fullstackpython.com/flask.html)

## How To Setup Flask on Plesk

### 1. Create a directory on your main domain called `flasktest`.  

If you were transferred from the old cPanel, your main domain will be parked on the `public_html` directory.  

If you created a new account on Plesk, your directory will be `httpdocs`.

### 2. Create an `.htaccess` file inside the `flasktest` directory with these contents:

```text
Options +ExecCGI
RewriteEngine On
RewriteBase /
RewriteRule ^(media/.*)$ - [L]
RewriteRule ^(admin_media/.*)$ - [L]
RewriteRule ^(flask\.wsgi/.*)$ - [L]
RewriteRule ^(.*)$ flasktest/flask.wsgi/$1 [QSA,PT,L]
```

### 3. Create a file named `flask.wsgi` inside the `flasktest` directory with these contents:

```text
import os, sys

# edit your path below
sys.path.append("/home/domain.helioho.st/httpdocs/flasktest");

sys.path.insert(0, os.path.dirname(__file__))
from myapp import app as application

# set this to something harder to guess
application.secret_key = 'secret'
```

### 4. Create a file named `myapp.py` inside the `flasktest` directory with these contents:

```text
import sys

from flask import Flask, __version__
app = Flask(__name__)
application = app

@app.route("/")
def hello():
  return """

    Flask is working on HelioHost.<br><br>
    <a href="/flasktest/python/version/">Python version</a><br>
    <a href="/flasktest/flask/version/">Flask version</a>

  """

@app.route("/python/version/")
def p_version():
  return "Python version %s<br><br><a href='/flasktest/'>back</a>" % sys.version

@app.route("/flask/version/")
def f_version():
  return "Flask version %s<br><br><a href='/flasktest/'>back</a>" % __version__

if __name__ == "__main__":
  app.run()
```

### 5. Make sure your directory structure and files look like this:

```text
flasktest/
├── flask.wsgi
├── .htaccess
└── myapp.py

0 directories, 3 files
```

### 6. If you did everything right it should look like the below:

Screenshot taken from [https://krydos.heliohost.org/flasktest/](https://krydos.heliohost.org/flasktest/)

![](../.gitbook/assets/flask_test.png)

{% hint style="warn" %}
Since WSGI uses server side caching, your changes might not appear immediately, and **in some cases might take several hours to update**.  

We recommend developing your Flask app on your home computer and hosting the production copy on the server.
{% endhint %}

## Troubleshooting

If you receive an error of `You don't have permission to access /flasktest/flask.wsgi/ on this server`, you may need to add `AddHandler cgi-script .py`to your `.htaccess` file.

## Running Flask at the Webroot

The above example is for Flask in a subdirectory, so users can host different projects in different subdirectories rather than dedicating the whole domain to one Flask app.

If you prefer to run Flask at the webroot instead, this is possible with some slight changes to the `.htaccess`, `flask.wsgi`, and `myapp.py` files.

### References

This tutorial is adapted from the **[How to Use Flask on Plesk](https://helionet.org/index/topic/53856-how-to-use-flask-on-plesk/)** post on the HelioNet forum, answered by Krydos.