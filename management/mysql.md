<a comment="Leveraging lists to create a manually created TOC.  Unfortunately, we cannot get rid of the bullet points.  Something is better than nothing."></a>
# Table Of Contents
* [MariaDB](#mariadb)
* [cPanel](#cpanel)
  * [Create](#cpanel-create)
    * [Create DB](#cpanel-create-step1)
    * [Create User](#cpanel-create-step2)
    * [Assign User to DB](#cpanel-create-step3)
  * [Access](#cpanel-access)
    * [localhost](#cpanel-access-local)
    * [PHPMyAdmin](#cpanel-access-phpmyadmin)
    * [Remote](#cpanel-access-remote)
* [Server Hosts](#server-hosts)
* [Example Code](#example-code)

# MariaDB <a id="mariadb"></a>

MariaDB is a very handy tool available to webmasters who want to take advantage of dynamic web pages which run on languages such as PHP, as well as softwares like WordPress that may have been manually installed \(not installed using Softaculous\).

More information about MariaDB can be found at [Wikipedia](https://en.wikipedia.org/wiki/MariaDB) and [official website](https://mariadb.org/).

# cPanel Procedure <a id="cpanel"></a>

The following are a list of steps to follow to create a MaraiDB in cPanel.

## Creating a database <a id="cpanel-create"></a>

Before you take advantage of MariaDB, you will need to create a database and a user to work with. To access the `MariaDB Databases` section of cPanel, use the button available on the homepage.

### Step 1: Creating the database <a id="cpanel-create-step1"></a>

In the `MariaDB Databases` section of cPanel, take a look at the `Create new database` section of the resulting page. Give your database a name and submit the form. In the resulting page, you should see your new database in the list of databases.

### Step 2: Creating the user <a id="cpanel-create-step2"></a>

Now scroll down to the `Create new user` section of the resulting page. Fill in a username and password \(a strong password is always good\) and submit the form. In the resulting page, you should see your new user in the list of users right at the bottom of the page.

### Step 3: Assign the user to the database <a id="cpanel-create-step3"></a>

In the `Add user to database` section of the resulting page, select your newly created user and your newly created database from the drop down, then submit the form. In the resulting page, give the user the appropriate privileges \(the commands the user can run\). If you are unsure, just click `All privileges` and submit the form. In the resulting page, in the list of databases, you should see your newly created user in `Users` column alongside your newly created database.

### Accessing the database <a id="cpanel-access"></a>

Below are some tips to connect to your database either through cPanel via phpmyadmin, locally via code, or remotely through code or other client \( eg. mysql command line or some other utility such as a GUI listed on the [MaraiDB website](https://mariadb.com/kb/en/graphical-and-enhanced-clients/) \).

#### Local connections <a id="cpanel-access-local"></a>

If you are connecting locally, then your `HOST` is `localhost`. Your database name is the name you specified, but prefixed with your cPanel username and then an underscore \(e.g. CPANEL\_DATABASE\).

#### Managing the database with phpMyAdmin <a id="cpanel-access-phpmyadmin"></a>

By using the phpMyAdmin button on cPanel's homepage, you can control and manage your databases and issue commands. More information about phpMyAdmin is available at the [official site](https://www.phpmyadmin.net).

#### Connecting Remotely <a id="cpanel-access-remote"></a>

**Step 1**

Login to your cPanel.

**Step 2**

Click on `Remote MariaDB`.

**Step 3**

Put a percent sign `%` for all IP or else enter the IP to give access to only that particular IP in the box and click `Submit`.

# Server Hosts <a id="server-hosts"></a> 

Use the host for your server:

* Tommy: `tommy2.heliohost.org`
* Ricky: `ricky.heliohost.org`
* Johnny: `johnny.heliohost.org`

# Example Code Links <a id="example-code"></a>
[MariaDB PHP Example](https://mariadb.com/resources/blog/how-to-connect-python-programs-to-mariadb/)

[MariaDB Python mariabd module example](https://mariadb.com/resources/blog/how-to-connect-python-programs-to-mariadb/)

[MariaDB Python sqlalchemy module example](https://mariadb.com/resources/blog/using-sqlalchemy-with-mariadb-connector-python-part-1/)

[PHP mysqli Docs](https://www.php.net/manual/en/book.mysqli.php)

[Python mariadb module docs](https://mariadb-corporation.github.io/mariadb-connector-python/)

[Python sqlalchemy module docs](https://docs.sqlalchemy.org/en/20/)