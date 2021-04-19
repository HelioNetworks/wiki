# Python

The easiest way to get started with Python on a server is with CGI. Really the only difference between CGI and running the script on your home computer is CGI needs to output a "Content-Type" header.

## Steps

* Open the File Manager in cPanel
* Double click `public_html`
* Double click `cgi-bin`
* In the top left click `+ File`
* Type `test.py` as your filename
* Click `Create New File`
* Highlight the `test.py` file and click `Permissions`
* Check execute on all three columns so it says `755`
* Click `Change Permissions`
* Click `reload` and make sure the `755` shows up under the permissions column
* Highlight `test.py` and click `Editor`
* Leave `UTF-8` as the encoding and click `Edit`
* Copy/paste this in:

  ```text
  #!/usr/bin/python3.7

  print("Content-Type: text/html\n\n")

  print("Heliohost rules!")
  ```

* Click `Save Changes`
* Go to `<your subdomain>.heliohost.org/cgi-bin/test.py`

If everything worked it should say `Heliohost rules!` in your browser. The first line is the shebang. That's what tells the server which version of python to use. On Tommy and Johnny you can pick between:

| Path | Version |
| :--- | :--- |
| \#!/usr/bin/python2.7 | 2.7.13 |
| \#!/usr/bin/python3.7 | 3.7 |

and `python3.6` for Ricky.

The next line is the `Content-Type` header. This is important so the server knows what to do with the output that follows. If you forget it your script will give a useless 500 error. The content type header always has to have the two end lines immediately after it. That's what the `\n\n` is.

## Modules

You can see the modules that are currently installed on the Python versions:

## Johnny

* [Python 2.7](https://krydos2.heliohost.org/cgi-bin/modules27.py)
* [Python 3.7](https://krydos2.heliohost.org/cgi-bin/modules37.py)

### Ricky

* [Python 2.7](https://krydos1.heliohost.org/cgi-bin/modules27.py)
* [Python 3.6](https://krydos1.heliohost.org/cgi-bin/modules36.py)

### Tommy

* [Python 2.7](https://krydos.heliohost.org/cgi-bin/modules27.py)
* [Python 3.7](https://krydos.heliohost.org/cgi-bin/modules37.py)

If you don't see the module you need your script will probably give a useless 500 error when you try to import the missing module. Just make a post on the [forums](https://www.helionet.org/index/forum/45-customer-service/) stating your server, the version of python you're using, and the module\(s\) you need.

## Extra: Python scripts outside cgi-bin folders

Executing a CGI script outside the `cgi-bin` folder is possible with some modifications.

### Steps

* Go to `/home/<your username>/public_html`.
* Create a file named `.htaccess` and copy/paste this in:

  ```text
  Options +ExecCGI
  AddHandler cgi-script .py
  DirectoryIndex index.py
  ```

The first two lines make `.py` files executable outside `cgi-bin`, and the last line makes the filename `index.py` show up if someone goes to your domain without having to type out the filename like `domain.heliohost.org/index.py`. This also supports other CGI file extensions.

