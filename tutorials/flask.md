# Flask

## Preface

This tutorial is adapted from a forum post answered by Krydos, [How do I use Flask](https://www.helionet.org/index/topic/27822-how-do-i-use-flask-on-johnny/?p=128919) on the HelioNet forum.

It is worth to note that flask on the Tommy and Johnny servers use python 3.7, and if you want to use flask on python 2.7 you have to be on the Ricky server.

## About Flask

Flask is a Python web framework built with a small core and easy-to-extend philosophy. [Full Stack Python](https://www.fullstackpython.com/flask.html)

## How to setup Flask

Create a folder in public\_html called flask

```text
/home/username/public_html/flask/
```

In that folder create a .htaccess file:

```text
RewriteEngine On
RewriteBase /
RewriteRule ^(media/.*)$ - [L]
RewriteRule ^(admin_media/.*)$ - [L]
RewriteRule ^(flask\.wsgi/.*)$ - [L]
RewriteRule ^(.*)$ flask/flask.wsgi/$1 [QSA,PT,L]
```

Create a file named flask.wsgi in the flask directory.

```text
import os, sys

# edit your username below
sys.path.append("/home/username/public_html/flask")

sys.path.insert(0, os.path.dirname(__file__))
from myapp import app as application

# make the secret code a little better
application.secret_key = 'secret'
```

Create a python script named myapp.py in the flask directory.

```text
import sys

from flask import Flask, __version__
app = Flask(__name__)
application = app

@app.route("/")
def hello():
  return """

    HelioHost rules!<br><br>
    <a href="/flask/python/version/">Python version</a><br>
    <a href="/flask/flask/version/">Flask version</a>

  """

@app.route("/python/version/")
def p_version():
  return "Python version %s" % sys.version

@app.route("/flask/version/")
def f_version():
  return "Flask version %s" % __version__

if __name__ == "__main__":
  app.run()
```

