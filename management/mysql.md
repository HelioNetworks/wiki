<a comment="Leveraging lists to create a manually created TOC.  Unfortunately, we cannot get rid of the bullet points.  Something is better than nothing."></a>
<a id="top"></a>
# Table Of Contents
* [MariaDB](#mariadb)
* [Plesk](#plesk)
  * [Create](#plesk-create)
    * [Create DB](#plesk-create-step1)
    * [Create User](#plesk-create-step2)
  * [DB User Permissions](#plesk-user-permissions)
    * [DB User Editing](#plesk-user-editing)
  * [Access](#plesk-access)
    * [localhost](#plesk-access-local)
    * [PHPMyAdmin](#plesk-access-phpmyadmin)
    * [Remote](#plesk-access-remote)
* [Server Hosts](#server-hosts)
* [Example Code](#example-code)

[Top](#top)<a id="mariadb"></a>
# MariaDB 

MariaDB is a very handy tool available to webmasters who want to take advantage of dynamic web pages which run on languages such as PHP, as well as softwares like WordPress that may have been manually installed \(not installed using Softaculous\).

More information about MariaDB can be found at <a href="https://en.wikipedia.org/wiki/MariaDB" target="_blank">Wikipedia</a> and <a href="https://mariadb.org/" target="_blank">official website</a>.

[Top](#top)<a id="plesk"></a>
# Plesk Procedure 

The following are a list of steps to follow to create a MaraiDB in Plesk.

[Top](#top)<a id="plesk-create"></a>
## Navigating to the `Databases` Section 

Before you take advantage of MariaDB, you will need to create a database and a user to work with. To access the `Databases` section of Plesk, use the button available left hand menu.  Depending on your resolution (.eg mobile devices), there may be a menu icon ( ☰ ) that you have to click to display the menu.  You can also access the `Database` section from the `Websites & Domains` section.

[Top](#top)<a id="plesk-create-step1"></a>
### Creating the Database 

In the `Databases` section of Plesk, there's a button `+ Add Database`. On smaller resolutions, the menu icon will appear.  On the resulting page, you will have to fill out a form.

[Top](#top)<a id="cpanl-create-step1"></a>
#### General Section

The first section is general.  There are three items in this section.  

The first item is the database name, this is prefixed with the format`<Username>_`.  

The second item is the server.  This will be a dropdown of the available database servers.  From this dropdown select `localhost:3306( default for MariaDB )`. 

The third item is a drop down to associate your database with a site.  The default is no related sites.  From this dropdown you can associate your database with any website you have set up.  This is a convenience feature to help associate a database with a website and is not required.

[Top](#top)<a id="plesk-create-step2"></a>
#### User Section

The next section is `Users`.  In this section there are 5 items as well as two buttons.  

The first item is a checkbox to indicate whether or not you want to add a user while creating your database.  This is checked by default.

The second item is the username, this will have a prefix of the same format as the database name.

The third item is the password.  This item is associated with the two buttons.  The `Generate` button will generate a password for you.  The second button will display the password on your screen.  Generated passwords are hidden by default unless the show button is pressed.  You can also enter any password you require.  Once a password is entered a `Password Strength` meter will appear.  There is a help button `(?)` with more details regarding this meter.

The fourth item is a confirm password.  This must match the password.

The fifth item is a checkbox to indicate a `User has access to all databases within the selected subscription`.  This means the user can access all databases listed in the main `Databases` section.

The sixth item is access control.  You have three choices.  You can allow local only connections.  You can allow connections from any IP, or you can submit a list of IPs or FQDNs.  This list supports wildcards and examples are provided.

Once these sections are complete, you can click `OK` to create the database.


[Top](#top)<a id="plesk-user-permissions"></a>
### DB User Permissions

In order to change user permissions and privileges, you have to navigate to the user.  This is done from the `Databases` section.  A list of users will be listed next to your databases.  Click on the user you want to modify to proceed to the `Edit Database User` screen.

[Top](#top)<a id="plesk-user-editing"></a>
#### DB User Editing

The first section of this screen is identical to the [user section](#plesk-create-step2) while creating the database and will not be covered here.

There are two items available while editing a user that aren't available while creating a database.  

You can assign roles: Read & Write, Read Only, Write Only, and Customer.  There are also data/sturcture access which will specify which privileges a DB user has.  See the [MariaDB privileges documentaion](https://mariadb.com/docs/server/ref/mdb/privileges/) for more details on the individual privileges.

[Top](#top)<a id="plesk-access"></a>
### Accessing the database 

Below are some tips to connect to your database either through cPanel via phpmyadmin, locally via code, or remotely through code or other client \( eg. MariaDB's mysql command line or some other utility such as a GUI listed on the [MaraiDB website](https://mariadb.com/kb/en/graphical-and-enhanced-clients/) \).

[Top](#top)<a id="plesk-access-local"></a>
#### Local connections 

If you are connecting locally, then your `HOST` is `localhost`. Your database name is the name you specified, but prefixed with your cPanel username and then an underscore \(e.g. CPANEL\_DATABASE\).

[Top](#top)<a id="plesk-access-phpmyadmin"></a>
#### Managing the database with phpMyAdmin 

By using the phpMyAdmin button on cPanel's homepage, you can control and manage your databases and issue commands. More information about phpMyAdmin is available at the [official site](https://www.phpmyadmin.net).

[Top](#top)<a id="plesk-access-remote"></a>
#### Connecting Remotely 

**Step 1**

Login to your cPanel.

**Step 2**

Click on `Remote MariaDB`.

**Step 3**

Put a percent sign `%` for all IP or else enter the IP to give access to only that particular IP in the box and click `Submit`.

[Top](#top)<a id="server-hosts"></a>
# Server Hosts  

Use the host for your server:

* Tommy: `tommy2.heliohost.org`
* Ricky: `ricky.heliohost.org`
* Johnny: `johnny.heliohost.org`

[Top](#top)<a id="example-code"></a>
# Example Code Links
These links should open a new browser tab or window.

Official MariaDB blogs:

<a href="https://mariadb.com/resources/blog/how-to-connect-python-programs-to-mariadb/" target="_blank">PHP Example</a>

<a href="https://mariadb.com/resources/blog/how-to-connect-python-programs-to-mariadb/" target="_blank">Python mariabd module example</a>

<a href="https://mariadb.com/resources/blog/using-sqlalchemy-with-mariadb-connector-python-part-1/" target="_blank">Python sqlalchemy module example</a>

Offical PHP and Python module docs:

<a href="https://www.php.net/manual/en/book.mysqli.php" target="_blank">PHP mysqli Docs</a>

<a href="https://mariadb-corporation.github.io/mariadb-connector-python/" target="_blank">Python mariadb module docs</a>

<a href="https://docs.sqlalchemy.org/en/20/" target="_blank">Python sqlalchemy module docs</a>

You can find other language examples using your favourite search engine.