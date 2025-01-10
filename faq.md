# FAQ

## ETA for New Features and Server Repairs

{% hint style="info" %}
For information on ETAs for new features or server fixes, please review our [Repair Times](hosting/repair-times.md) page.
{% endhint %}

## Your homepage says "Professional-Grade Hosting", but your support sucks / isn't helping me / is run by a number of volunteers, what gives?‌

There is a difference between "Professional-Grade Hosting" and "Professional-Grade Customer Support". Most people are used to having dedicated customer support staff that will answer every little question; this comes standard with paid hosting. However, we don't do that here. Among the five of us, we have the collective knowledge and technical expertise of any other support staff, but in order for us to help you, we expect from you a certain competency. You must try to spell and use grammar correctly (to the best of your ability). You must provide necessary information (e.g. **username** and **domain name**). You must be able to read instructions, and you must be able to follow instructions. We will treat you with respect and professionalism if you follow these guidelines. We will probably be very annoyed if u tyep liek dis.‌

## I log in frequently but am still receiving inactivity emails, what gives?

If you have an account on [Tommy](servers/virtual/tommy.md) or [Johnny](servers/virtual/johnny.md), to ensure that your logins are logged, log in to [heliohost.org](https://heliohost.org) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Each time you do so your last login date is set to the current time. Your account will then remain active for another 30 days. For more details, review our [Inactivity Policy](accounts/suspension-policy.md#inactivity-policy).

## Why must all posts on HelioNet be in English?

The support staff is fluent and reliable only in English.

## Why does HelioHost crash?

Sometimes users will abuse server resources and cause the server to crash. We try to fix this as quickly as we can. Since the servers and Plesk are handling such a high volume of users, errors are bound to come up. We also try to fix these ASAP. Also, when [djbob](misc/staff/ashoat.md) works on the server, he occasionally screws up, which also causes crashes.

## Why was my account suspended?

Our [Suspension Policy](accounts/suspension-policy.md) provides comprehensive details on why we will suspend accounts.

A few common reasons for account suspensions are: 

- [Terms of Service](hosting/terms.md) violation(s).
- [Account Inactivity](accounts/suspension-policy.md#inactivity-policy) on our [Johnny](servers/virtual/johnny.md) and [Tommy](servers/virtual/tommy.md) servers. Renew your account [here](http://heliohost.org/renew/).
   - Our [Morty](servers/virtual/morty.md) server has no login requirement. As long as there is a positive balance on your account, it will remain active.
- [Duplicate Accounts](accounts/suspension-policy.md#duplicate-accounts). The limit is **1 account per human being**.
- Exceeding the [Account Storage](accounts/suspension-policy.md#account-storage-limits) limits. On [Johnny](servers/virtual/johnny.md), [Tommy](servers/virtual/tommy.md), and [Morty](servers/virtual/tommy.md) we offer 1000 MB of free web space. For users who need more storage, we provide one-time paid donation options for [increased account storage](accounts/donation-increase-storage.md) or you can request that an admin delete specific files/folders for you. We also offer a range of [VPS Plans](https://heliohost.org/vps/) with a 10% discount when you pay for 6 months upfront.
- Exceeding the [High Server Usage](accounts/suspension-policy.md#high-server-usage) limits on our [Johnny](servers/virtual/johnny.md) and [Tommy](servers/virtual/tommy.md) servers. We enforce a memory limit of no more than 100 GB and a CPU limit of 10,000 per day. You can monitor your load numbers on [the load page within your dashboard](https://heliohost.org/dashboard/load/).
   - Our [Morty](servers/virtual/morty.md) server also has a memory limit of no more than 100 GB and a CPU limit of 10,000 per day. If you exceed these limits, instead of suspending your account, we will charge you for the overages.

It is also possible that this was an error in our system. If you suspect that this is the case, report the error in a new post [here](https://helionet.org/index/forum/81-suspended-and-queued-accounts/), making sure to provide your **username**.

## Why does my new subdomain show a "Queued" page?

{% hint style="info" %}
All domain and subdomain changes take **up to 2 hours** to go into effect as they require an Apache restart. 
{% endhint %}

During the first 2 hours, seeing the queued page is normal and only means the change hasn't taken effect yet. If it's been longer than **a full 2 hours**, try [clearing your browser cache](misc/clear-your-cache.md).

## Why can't I log in?

{% hint style="info" %}
If you just registered, please wait **up to 2 hours** for your Plesk account to become fully active.
{% endhint %}

If it has been longer than **a full 2 hours** since you registered and you still see an `Account Queued` page, try [clearing your browser cache](misc/clear-your-cache.md). If you are still experiencing problems, make sure you are entering your username in all lowercase letters, i.e. "wizard", not "Wizard" or "WIZARD".

## How do I keep my account active / prevent being suspended?

If you have an account on [Tommy](servers/virtual/tommy.md) or [Johnny](servers/virtual/johnny.md), login to [heliohost.org](https://heliohost.org) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Each time you do so your last login date is set to the current time. Your account will then remain active for another 30 days. For more details, review our [Inactivity Policy](accounts/suspension-policy.md#inactivity-policy).

On our paid subscription server, [Morty](servers/virtual/morty.md), as long as there is a positive balance on your account, it will remain active without needing to log in.

## What is a Daily Signup Limit and why is it stopping me from registering?

Each server has a daily limit for sign-ups so that it doesn't crash from all the people wanting to use HelioHost. Free signups on Johnny now reset [every 12 hours](https://helionet.org/index/topic/59660-midnight-and-noon/) at midnight UTC and noon UTC. Please see our [list of helpful tips for getting a free account on Johnny](./hosting/signing-up.md#helpful-tips-for-getting-a-free-account-on-johnny).

## What if I have at least $1 and don't want to wait to sign up?

We offer various [Donor Plans](https://heliohost.org/tommy/), so for a one-time donation of as little as $1 USD, you can open an account any time of day.

Users on our Tommy donor server and the free Johnny server are [required to log in at least once a month](./accounts/suspension-policy.md#inactivity-policy) to keep their accounts active. 

## What other options are available if I want to sign up right away?

For users who prefer not to have to log in regularly, our [Morty](servers/virtual/morty.md) paid subscription server has no login requirement as long as there is a positive balance on your account.

We also offer a range of [VPS Plans](https://heliohost.org/vps/), with a 10% discount when you pay for 6 months upfront.

## My account was deleted. Can I get my data back?

No. We do not keep backups of your data nor is it our responsibility to, as mentioned in our [Terms of Service](hosting/terms.md). You must backup your own data regularly.  

If you're not sure how to backup your data, please see our [Account Backups](tutorials/plesk/account-backups.md) tutorial page. It contains guidance on creating manual backups which you can download to your local machine, and instructions for setting up scheduled automated backups within Plesk.

## Can I have more than one account?

No. It's [one account per user](accounts/suspension-policy.md#duplicate-accounts). This means that you cannot have more than 1 account, even if you use different email addresses. The limit is **1 account per human being**.

## How do I reset my hosting account to start fresh?

Because wiping an account is destructive, we have to verify your identity before we do so. This is to prevent someone from pretending to be you and deleting all your data.

To request that we reset your account so you can start over, send an email **from the same email address as your hosting account** to `support@heliohost.org` so we can verify your identity and wipe your account. Alternatively, you can make a post on the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) from a forum account with the same email address as your hosting account. If you're not sure what email address is associated with your hosting account, you can check by logging into Plesk and navigating to: **Account > My Profile > General > External email address**

Once your account has been reset, you will receive an email with a link to restart your account. **You will have 7 days to use the link.** If you don't use the link to restart your account within 7 days, you will need to signup for a brand new account.

If you had WSGI Control Access on your account for [Flask](tutorials/flask.md) or [Django](tutorials/django/README.md) and you want this re-enabled after the reset, you will need to re-request WSGI Control Access after the reset has been completed. By default, account resets will disable WSGI Control Access.

## VPS Rebuilds

Due to certain users abusing our generosity in the past and requesting 50 or so rebuilds in less than a month, we now limit each VPS to **1 free rebuild per month**. 

## Purchasing Additional VPS Rebuilds

If you need to purchase an additional VPS rebuild, please use the link below to donate $1 USD:

{% embed url="https://www.paypal.com/ncp/payment/6Z88J5KJZJ3RJ" caption="Donate $1 USD for VPS Rebuild" %}

After you have made the donation, please provide your [PayPal Transaction ID](accounts/donation-increase-storage.md#paypal-transaction-id) as part of your VPS rebuild request, so the donation can be verified.

## How do I request a VPS rebuild?

Because rebuilding a VPS is destructive, we have to verify your identity before we do so. This is to prevent someone from pretending to be you and deleting all your data.

To request that we rebuild your VPS, send an email **from the same email address as your VPS account** to `support@heliohost.org` so we can verify your identity and rebuild your VPS. If you would like a free dashboard (Hestia, KeyHelp, etc.) installed after the rebuild, please include this in the request.  

Alternatively, you can make a post on the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) from a forum account with the same email address as your VPS account. If you're not sure what email address is associated with your VPS account, you can check by logging into the [VPS Dashboard](https://heliohost.org/login/) with your VPS Username and Password. The email address attached to your VPS account will be displayed at the top right of the page.  

## How do I delete my hosting account?

To delete your HelioHost Plesk account, go to your dashboard and click on the [Delete your account and remove all content](https://heliohost.org/dashboard/delete/) button.

To delete your HelioNet Forum account, post a topic in the [Contact HelioNet forum](https://helionet.org/index/forum/4-contact-helionet/?do=add).

## How do I change my main domain?

To change the main domain on your HelioHost Plesk account, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **full domain name** you want as your main domain, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)

{% hint style="warning" %}  
There is a risk of data loss when main domains are changed. We strongly recommend you [create an account backup](../tutorials/plesk/account-backups.md#making-your-own-manual-account-backup) before requesting to change your main domain.  

As mentioned in our [Terms of Service](../hosting/terms.md), it is not HelioHost's responsibility to keep backups of your data.  
{% endhint %}

As an alternative to changing your main domain, consider using [Parked (Alias)](alias-parked-domains.md), [Addon](addon-domains.md), and/or [Subdomains](subdomains.md).

## What are the nameservers for HelioHost?

* `ns1.heliohost.org`
* `ns2.heliohost.org`

## What IP addresses should I add to my DNS?

To add A (IPv4) or AAAA (IPv6) records to your domain registrar's dashboard, follow these steps to view the IP addresses for your server:  

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

## Can I PM an administrator for help?

No, do not PM the administrators expecting support unless we explicitly tell you to. Please use the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/) instead. Also, in order for us to provide the best and most efficient support, please provide your **username**, **domain name**, and **server name** along with any requests. If you are sending your support request via email to `support@heliohost.org`, make sure to contact us **from the same email address as your hosting account**.

## The server is slow / Feature XYZ doesn't work / Something's wrong with my account / etc.

Please post the issue in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/) and we will try to solve the problem. Also, in order for us to provide the best and most efficient support, please provide your **username**, **domain name**, **server name**, and any **error messages** you are encountering.

## Can Feature XYZ be installed?

Softaculous [returned in March 2024](https://helionet.org/index/topic/59683-softaculous-has-returned/) and is offered on our [Tommy](servers/virtual/tommy.md), [Johnny](servers/virtual/johnny.md), and [Morty](servers/virtual/morty.md) servers, making it possible to install the latest version of 459 different software packages with just a single click.

To browse the available options, login to Plesk and select Softaculous from the menu:

![](.gitbook/assets/softaculous_menu_item.png) 

If you need a system-wide feature installed, please post a request in our [Customer Service forum](https://helionet.org/index/forum/45-customer-service/), making sure to provide your **username**, **domain name**, **server name**, and any applicable **version numbers**.

## Can I use SSH?

On hosting accounts, secure shell access (SSH) is disabled for security reasons. 

However, it is possible to run jailed shell commands using Plesk's [Scheduled Tasks (cron jobs)](tutorials/plesk/cron-jobs.md) feature. 

In many cases, SSH is not actually necessary. Please post a request in our [Customer Service forum](https://helionet.org/index/forum/45-customer-service/), making sure to provide your **username**, **domain name**, **server name**, and **the command you want to run**, and we'll be happy to investigate other ways to accomplish the same task without SSH.

If you absolutely require SSH access, you will need a [VPS](https://heliohost.org/vps/). We offer a range of VPS plans, and a 10% discount when you pay for 6 months upfront.

## Does HelioHost support sockets? Which ports are open?

Our [Tommy](servers/virtual/tommy.md), [Johnny](servers/virtual/johnny.md), and [Morty](servers/virtual/morty.md) servers have zero inbound ports available to be opened. All ports that are currently open already have services listening, such as 80 http, 443 https, 3306 MariaDB, and 5432 PostgreSQL. 

Outbound ports are similar: ports like 80, 443, 3306, 5432, 25, 465, etc., are open to allow scripts to connect to common services on remote servers.

If you can proxy your websocket through Apache or Nginx, it can work without opening a port:  
* You could use an `.htaccess` file to proxy the websocket connection through Apache.
* With the help of a root admin, you could get an Nginx proxy set up. To explore this option, please post a request in our [Customer Service forum](https://helionet.org/index/forum/45-customer-service/), making sure to provide your **username**, **domain name**, **server name**, and **details about your websocket application**, and we'll be happy to help.

If you absolutely need a port opened, you'll need to get one of our [VPS Plans](https://heliohost.org/vps/), and you will then have all 65535 ports available to open or close as you want. We offer a range of VPS plans, and a 10% discount when you pay for 6 months upfront.

## Are directory indexes enabled?

Yes. Directory indexes have been enabled by default on the shared hosting servers since late 2024. This is a feature many users have requested over the past few years, but if you don't want directory listings for a folder, simply create an empty `index.html` file inside it. Please check our [Directory Index](tutorials/plesk/create-website.md#directory-index) section for further information.

## Can I change my document root directory?

Typically, your domain root directory is `httpdocs` (or `public_html` if you were transferred from the old cPanel). Users cannot change the document root themselves inside Plesk. 

If you have a legitimate reason for needing the document root changed, please create a post in our [Customer Service forum](https://helionet.org/index/forum/45-customer-service/) and make sure to provide your **username**, **domain name**, **server name**, **the new document root directory you want**, and a **valid reason** explaining why you are unable to use your existing document root. The admins will review your request to determine if the change can be made.

## Can I use your services to mine cryptocurrency?

No. We do not allow mining on any of our plans (free or paid).

## Your hosting SUCKS! So do YOU!!!

Please see [this](http://helionet.org/index/topic/4723-suspended/page__p__46231#entry46231).

## I still have a question about HelioHost.

Post in the [Questions forum](https://helionet.org/index/forum/48-questions/) and we'll try to help you the best we can.