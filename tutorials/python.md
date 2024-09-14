# Python

The easiest way to get started with Python on a server is with CGI. The only real difference between CGI and running the script on your home computer is that CGI needs to output a `Content-Type` header.

## Python Versions Available

### Johnny server

| Server  | Python Version | Python Path           | Python Modules Installed                                 |
| :-----: | :------------: | :-------------------: | :------------------------------------------------------: |
| Johnny  | 3.9            | #!/usr/bin/python3.9  | [View](https://krydos2.heliohost.org/pyinfo/info3.9.py)  |
| Johnny  | 3.12           | #!/usr/bin/python3.12 | [View](https://krydos2.heliohost.org/pyinfo/info3.12.py) |

### Tommy server

| Server | Python Version | Python Path           | Python Modules Installed                                 |
| :----: | :------------: | :-------------------: | :------------------------------------------------------: |
| Tommy  | 3.9            | #!/usr/bin/python3.9  | [View](https://krydos1.heliohost.org/pyinfo/info3.9.py)  |
| Tommy  | 3.12           | #!/usr/bin/python3.12 | [View](https://krydos1.heliohost.org/pyinfo/info3.12.py) |

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
* Highlight the `test.py` file and select `Open in Browser` (Or manually navigate to: `<your subdomain>.helioho.st/cgi-bin/test.py`)

If everything worked, you should see `Heliohost rules!` displayed in your browser. 

## Code Explanation

In the code pasted in, the first line is called the `shebang`. It tells the server which version of Python to use. 

The second line of code is the `Content-Type` header. This is important so the server knows what to do with the output that follows. If you forget it, your script will give you an error. The `Content-Type` header always has to have the two end lines immediately after it. That's what the two `` `\n` `` are.

### Troubleshooting

If you don't see the module you need, your script will probably give you an error when you try to import the missing module. You can [view your account error logs](../tutorials/plesk/view-error-logs.md) for details on which module is missing and causing the error.

## Request Additional Python Modules

To request additional modules, please create a post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide **your account username**, **your server**, the **version of Python you're using**, and **the module(s) you need** including any relevant **version numbers** for them.

## Running Python scripts outside cgi-bin folder

Executing a CGI script outside the `cgi-bin` folder is possible with some modifications.

### Steps

* Go to `/home/<your username>/httpdocs`. (If you were transferred from the old cPanel, the folder will be called `public_html`)
* Create a file named `.htaccess` and copy/paste the below in:
```
Options +ExecCGI
AddHandler cgi-script .py
DirectoryIndex index.py
```
The first two lines make `.py` files executable outside `cgi-bin`, and the last line makes the filename `index.py` show up if someone goes to your domain without having to type out the filename like `domain.helioho.st/index.py`. This also supports other CGI file extensions.

## Further Support

If this tutorial has not worked for you, please go back and check all of your steps again to make sure you didn't miss anything. If you can't figure out what is wrong, please post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username** and any **error message(s)** received.