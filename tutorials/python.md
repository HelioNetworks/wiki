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
#!/usr/bin/python3.12

print("Content-Type: text/html\n\n")

print("Heliohost rules!")
```
* Click the `Save` button
* Highlight the `test.py` file and select `Open in Browser` (Or manually navigate to: `<your subdomain>.heliohost.org/cgi-bin/test.py`)

If everything worked, you should see `Heliohost rules!` displayed in your browser. 

## Code Explanation

In the code pasted in, the first line is called the `shebang`. It tells the server which version of Python to use. 

## On the Johnny server, you can pick between:

| Server  | Python Version | Python Path           | Python Details                                                  |
| :-----: | :------------: | :-------------------: | :-------------------------------------------------------------: |
| Johnny  | 3.9            | #!/usr/bin/python3.9  | [Python 3.9](https://krydos2.heliohost.org/pyinfo/info3.9.py)   |
| Johnny  | 3.12           | #!/usr/bin/python3.12 | [Python 3.12](https://krydos2.heliohost.org/pyinfo/info3.12.py) |

### Python 3.12 Modules Installed on Johnny

asgiref==3.8.1  
blinker==1.8.2  
click==8.1.7  
Django==5.0.7  
Flask==3.0.3  
itsdangerous==2.2.0  
Jinja2==3.1.4  
MarkupSafe==2.1.5  
python-dotenv==1.0.1  
sqlparse==0.5.1  
Werkzeug==3.0.3  

## On the Tommy server, you can pick between:

| Server | Python Version | Python Path           | Python Details                                                 |
| :----: | :------------: | :-------------------: | :------------------------------------------------------------: |
| Tommy  | 2.7            | #!/usr/bin/python2.7  | [Python 2.7](https://krydos.heliohost.org/pyinfo/info2.7.py)   |
| Tommy  | 3.6            | #!/usr/bin/python3.6  | [Python 3.6](https://krydos.heliohost.org/pyinfo/info3.6.py)   |
| Tommy  | 3.10           | #!/usr/bin/python3.10 | [Python 3.10](https://krydos.heliohost.org/pyinfo/info3.10.py) |

The second line of code is the `Content-Type` header. This is important so the server knows what to do with the output that follows. If you forget it your script will give a useless 500 error. The `Content-Type` header always has to have the two end lines immediately after it. That's what the `\n` is.

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