# Python

The easiest way to get started with Python on a server is with CGI. The only real difference between CGI and running the script on your home computer is that CGI needs to output a `Content-Type` header.

## Steps

* Open the File Manager in Plesk
* Open the `httpdocs` webroot directory. (If you were transferred from the old cPanel, the directory will be called `public_html`.)
* Open the `cgi-bin` directory
* In the top left click the `+` button and select `Create File`
* Type `test.py` as your filename
* Click `OK` to create the file
* Highlight the `test.py` file and select `Change Permissions`
* Add a checkmark to the `Execute / Search` column for all three rows (Owner / Group / Others)
* Click the `Save` button
* Make sure `rwx r-x r-x` (`755`) is displayed under the Permissions column
* Highlight `test.py` and select `Edit in Text Editor`
* Leave `UTF-8` as the encoding, set `Line break type` to `Convert to Unix style` and copy/paste the below into the large text field:
```
#!/usr/bin/python3.10

print("Content-Type: text/html\n\n")

print("Heliohost rules!")
```
* Click the `Save` button
* Highlight the `test.py` file and select `Open in Browser` (Or manually navigate to: `<your subdomain>.heliohost.org/cgi-bin/test.py`)

If everything worked, you should see `Heliohost rules!` displayed in your browser. 

### Code Explanation

In the code pasted in, the first line is called the `shebang`. It tells the server which version of Python to use. On Tommy and Johnny, you can pick between:

| Path                  | Version |
| ----------------------| ------- |
| #!/usr/bin/python2.7  | 2.7     |
| #!/usr/bin/python3.6  | 3.6     |
| #!/usr/bin/python3.10 | 3.10    |

The second line of code is the `Content-Type` header. This is important so the server knows what to do with the output that follows. If you forget it your script will give a useless 500 error. The `Content-Type` header always has to have the two end lines immediately after it. That's what the `\n` is.

## Modules

You can see the modules that are currently installed on the Python versions:

### Johnny

* [Python 2.7](https://krydos2.heliohost.org/pyinfo/info2.7.py)
* [Python 3.6](https://krydos2.heliohost.org/pyinfo/info3.6.py)
* [Python 3.10](https://krydos2.heliohost.org/pyinfo/info3.10.py)

### Tommy

* [Python 2.7](https://krydos.heliohost.org/pyinfo/info2.7.py)
* [Python 3.6](https://krydos.heliohost.org/pyinfo/info3.6.py)
* [Python 3.10](https://krydos.heliohost.org/pyinfo/info3.10.py)

If you don't see the module you need, your script will probably give a useless 500 error when you try to import the missing module. To request modules, please raise a request in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide **your server**, the **version of Python you're using**, and **the module(s) you need** including any relevant **version numbers** for them.

## Extra: Python scripts outside cgi-bin folders

Executing a CGI script outside the `cgi-bin` folder is possible with some modifications.

### Steps

* Go to `/home/<your username>/httpdocs`. (If you were transferred from the old cPanel, the folder will be called `public_html`)
* Create a file named `.htaccess` and copy/paste the below in:
```
Options +ExecCGI
AddHandler cgi-script .py
DirectoryIndex index.py
```
The first two lines make `.py` files executable outside `cgi-bin`, and the last line makes the filename `index.py` show up if someone goes to your domain without having to type out the filename like `domain.heliohost.org/index.py`. This also supports other CGI file extensions.
