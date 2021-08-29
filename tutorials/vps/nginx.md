# NGINX

## Preface

NGINX is described as a "web server that can also be used as a reverse proxy, load balancer, mail proxy and HTTP cache".
In practice, it's a powerful alternative to Apache, as it's more memory efficient. While configuring NGINX may seem a
little foreign if coming from Apache's `.htaccess` override based system, there's a lot to enjoy.

## Getting Started

While NGINX can be installed on a variety of systems, we'll focus on Ubuntu. As with most installations, it's highly
recommended to update your system beforehand, using `sudo apt update && sudo apt upgrade`.

{% hint style="danger" %} Using `sudo` is equivalent to running a command with root/administrative privileges! While
this tutorial relies heavily on its usage, most normal commands **should not** be run with the `sudo` prefix, as that's
a surefire way to potentially cause irreversible damage to your system configuration. {% endhint %}

With our system up-to-date, we can now run `sudo apt install nginx`. This command will install and configure a default
installation of NGINX, which means we should be able to access our VPS from a web browser...as soon as we configure our
firewall.

Using "UFW" (Universal Fire Wall), we can see using `sudo ufw app list` that NGINX has added three new profiles for us
to choose from ('Nginx Full', 'Nginx HTTP', 'Nginx HTTPS'). For our purposes, we'll enable 'Nginx Full'
using `sudo ufw allow 'Nginx Full'`. *Now* we should be able to see our VPS from a web browser, using
either `http://[Dedicated IPv4]` or `http://vps#.heliohost.us`, and see the default NGINX landing page.

## Configuring NGINX

### Creating a new content directory

While being able to see the default NGINX page is great, it's time to configure NGINX's "server blocks", which will
allow us to define how NGINX behaves on a "per-domain" basis. Let's start by creating a new directory for our web
content, using `sudo mkdir -p /var/www/[domain name]/html` (replace "[domain name]" with your own). In this case, `-p`
is used to create any missing parent directories, while `sudo` is used as the `/var` directory is system-protected.

Now, we can make our life easier by changing the owner and permissions of our new folder, so we won't have to repeatedly
use `sudo` permissions to access our own content. Using `sudo chown -R $USER:$USER /var/www/[domain name]/html`, we
can "change owner" to our current user (`-R` applies the command recursively to all the contents, if applicable). We
also need to set the directory's permissions, using `sudo chmod -R 755 /var/www/[domain name]` (chmod means "change
mode", while 755 is the numerical representation of "read and execute access for everyone, write access for the owner").

Any file we save in this new directory will be served using NGINX. As a simple test, we'll create a simple HTML file as
follows:

```html

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Home</title>
</head>
<body>
<h1>My NGINX Config is Working!</h1>
<p>Pat yourself on the back, for a job well done.</p>
</body>
</html>
```

### Creating a server block

For every domain that is associated with your VPS, you'll want to create an NGINX configuration file, known as a "server
block", located in `/etc/nginx/sites-available`. For example, we'll create one for our VPS
with `sudo vi /etc/nginx/sites-available/[domain name]` (no file ending like ".txt" or ".json", only your domain name)
. (For a brief Vim tutorial, see [here](#using-vim).) Enter "insert" mode using "i", and paste the following default
code block:

```
server {
        listen 80;
        listen [::]:80;

        root /var/www/[domain name]/html;
        index index.html index.htm index.nginx-debian.html;

        server_name yourdomain.com;

        location / {
                try_files $uri $uri/ =404;
        }
}

```

Once again, make sure to edit all the references to match your own domain name. Once you're finished, press "ESC",
followed by `:wq`. If you get an error saying "This file is readonly", make sure you are editing the file with `sudo`
permissions.

Now you may have noticed we created this configuration file in `sites-available`, **not** `sites-enabled`. Let's rectify
that, using a symbolic link (which is, in layman's terms, a shortcut for the system to find the original file in another
path). Using `sudo ln -s /etc/nginx/sites-available/[domain name] /etc/nginx/sites-enabled/`, we can accomplish that
task.

An easy way to check if everything's configured correctly, is to use `sudo nginx -t`, which will validate your NGINX
configuration.

To update our changes, we can use `sudo systemctl nginx restart`, which will restart NGINX.

Congratulations, you should now see your HTML page served from your VPS to your browser!

## Adding SSL

No website is complete (or secure) without SSL! As everyone else, we'll use [Let's Encrypt](https://letsencrypt.org/) to achieve this.

First, we'll need to install Certbot, which is a commandline utility for automating the process. Run `sudo apt install certbot python3-certbot-nginx` (**not the same as the Apache version**), which will install Certbot and its dependencies.

Now we can get a certificate. Run `sudo certbot --nginx -d yourdomain.com`, and follow the on-screen instructions to complete the process. Make sure you enabled SSL using UFW!

Your website will now be secure with SSL, and your SSL certificate will be automatically renewed every three months.

## Using Vim

Vim is the default text editor for most Unix based systems. While it's a ubiquitous program, it's infamous for being
hard to learn, especially since saving or exiting is not as intuitive as other comparable programs. However, it's not as
hard as it may seem.

To edit a file, use `vi file.txt`, which will open the Vim interface. If you supply a nonexistent filename, Vim will
create a file instead.

To enter "insert" mode, press "i". This will allow you to edit the current file, instead of running commands inside Vim.
To exit "insert" mode, press "ESC".

To save a file, make sure you are not in "insert" mode, before entering `:wq` (which will **write**, **quit**). If you
want to exit without saving your changes, enter `:q!`, which will **force quit**.
