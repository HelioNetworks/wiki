# WordPress

WordPress is a popular content management system (CMS) that allows users to easily create and manage websites.

However, WordPress is known to require a lot of server resources, as it's not very well optimized. Also, the more pages or plugins a WordPress site has, the bigger the site load will be.

Exceeding the account load limits will cause your user account to be [suspended for high server usage](/accounts/suspension-policy.md#high-server-usage).

{% hint style="warning" %}
If you use WordPress, we recommend you [monitor your site load here](https://heliohost.org/dashboard/load/)

If at any point you become concerned about your account server usage load getting you suspended, you can add "deny from all" to the bottom of your `.htaccess` file to take the site offline. Once that's been done, the site should stop generating load practically instantly.
{% endhint %}

## But my WordPress Site is Brand New / Has No Plugins / Gets Hardly Any Visitor Traffic

WordPress causes 0 load with 0 traffic, but sites built with WordPress are prime targets for bot attacks. When bots discover your site URL address, they will keep trying to hack in, which causes load on the server resources.

Even if your WordPress install is brand new, with no plugins, and your site gets few visitors, there is still a risk of suspension for high load due to bots spamming your site.

Additionally, a lot of free themes and plugins can be backdoors for hackers, and installing them comes with risks. Once bots access your site, they will 'phone home' which then enables hackers to change your site files, set up phishing sites, send spam from your account, etc.

## How Much Server Load Could It Cause?

Here are [some comparison calculations](https://helionet.org/index/topic/57357-solved-disconnect-addon-domain/?do=findComment&comment=252857) about how much demand on the server WordPress can cause.

## How Can I Keep My Server Load Low?

Our first recommendation is to switch to anything other than WordPress:

### WordPress Alternatives
* Some of our users have switched from WordPress to **Joomla** and liked it
* Another popular alternative is **Gatsby**. You can check out a guide on migrating your site [here](https://www.gatsbyjs.com/blog/2019-03-21-migrating-from-wordpress-to-gatsby/)
* For static blog generators, **Publii** may be an option for you. Please note that as it's local, you will need to upload every time you post. It's not for Android or iOS, and it cannot be synced unless you use a cloud syncing service for the local files. You can check out a guide on how to import data from your WordPress site into Publii [here](https://getpublii.com/docs/import-wordpress-into-static-html-site.html)
* **Jekyll** is a popular static site generator 
* **Hugo** is one of the most popular open-source static site generators
* **Grav** is an open-source flat-file CMS (Content Management System) 
* **Eleventy** (11ty) offers a simple 'zero-config' option to quickly get a site built

### How To Reduce WordPress Server Load

If moving away from WordPress is not an option for you, here are other things to try:
* Update everything to the latest version
* Disable uptime monitors
* Disable logins
* Disable unneeded plugins and themes
* Use caching plugins to reduce the load (users have mentioned that **WP Fastest Cache** plugin can be useful)
* Use Cloudflare caching
* Use Cloudflare and the **Super Page Cache for Cloudflare** WordPress plugin to [mitigate load spikes or other high load issues](https://helionet.org/index/topic/57606-handling-cpu-load-spikes-or-high-load-using-cloudflare/)
* Analyze access logs looking for IPs with thousands of page hits and blocking them in Cloudflare or `.htaccess`
* Convert to a static site (users have mentioned **WP2Static** as being a useful plugin that converts WordPress sites to static sites)
* Upgrade to a [VPS](https://heliohost.org/vps/)
