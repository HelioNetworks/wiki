# Creating MySQL Databases via cPanel

{% hint style="danger" %}
Please note that this wiki page is heavily outdated. Some information may be out of date, or entirely not work. An example is we don't use cPanel anymore.
{% endhint %}

MySQL is a very handy tool available to webmasters who want to take advantage of dynamic web pages which run on languages such as PHP, as well as softwares like WordPress that may have been manually installed (not installed using Softaculous).

More information about MySQL can be found at [Wikipedia](https://en.wikipedia.org/wiki/MySQL) and [official website](https://www.mysql.com).

## Creating a database

Before you take advantage of MySQL, you will need to create a database and a user to work with. To access the `MySQL Databases` section of cPanel, use the button available on the homepage.

### Step 1: Creating the database

In the `MySQL Databases` section of cPanel, take a look at the `Create new database` section of the resulting page. Give your database a name and submit the form. In the resulting page, you should see your new database in the list of databases.

### Step 2: Creating the user

Now scroll down to the `Create new user` section of the resulting page. Fill in a username and password (a strong password is always good) and submit the form. In the resulting page, you should see your new user in the list of users right at the bottom of the page.

### Step 3: Assign the user to the database

In the `Add user to database` section of the resulting page, select your newly created user and your newly created database from the drop down, then submit the form. In the resulting page, give the user the appropriate privileges (the commands the user can run). If you are unsure, just click `All privileges` and submit the form. In the resulting page, in the list of databases, you should see your newly created user in `Users` column alongside your newly created database.

## Accessing the database

### Your database details

If you are connecting locally, then your `HOST` is `localhost`. Your database name is the name you specified, but prefixed with your cPanel username and then an underscore (e.g. CPANEL\_DATABASE).

### Managing the database with phpMyAdmin

By using the phpMyAdmin button on cPanel's homepage, you can control and manage your databases and issue commands. More information about phpMyAdmin is available at the [official site](https://www.phpmyadmin.net).

### Connecting to the database through PHP

Create a blank PHP file, enter:

```
<?php
$mysqli = new mysqli("HOST", "USERNAME", "PASSWORD", "DATABASE");
if (mysqli_connect_errno()) {
printf("Connect failed: %s\n", mysqli_connect_error()); //this will print out the error while connecting to MySQL, if any
exit();
}
?>
```

To execute a query via PHP:

```
<?php
$mysqli = new mysqli("HOST", "USERNAME", "PASSWORD", "DATABASE");
$sql="SELECT * FROM `TABLE`";
$result = mysqli_query($mysqli,$sql);
?>
```

Filling your HOST, USERNAME, PASSWORD, and DATABASE with the actual information.

### Connecting Remotely

**Step 1**

Login to your cPanel.

**Step 2**

Click on `Remote MySQL`.

**Step 3**

Put a percent sign `%` for all IP or else enter the IP to give access to only that particular IP in the box and click `Submit`.

**Step 4**

Use the host for your server:

* Tommy: `tommy.heliohost.org`
* Ricky: `ricky.heliohost.org`
* Johnny: `johnny.heliohost.org`
