# FAQ

## ETA for New Features and Server Repairs

{% hint style="info" %}
For information on ETAs for new features or server fixes, please review our [Repair Times](hosting/repair-times.md) page.
{% endhint %}

## Your homepage says "Professional-Grade Hosting", but your support sucks / isn't helping me / is run by a number of volunteers, what gives?‌

There is a difference between "Professional-Grade Hosting" and "Professional-Grade Customer Support". Most people are used to having dedicated customer support staff that will answer every little question; this comes standard with paid hosting. However, we don't do that here. Among the five of us, we have the collective knowledge and technical expertise of any other support staff, but in order for us to help you, we expect from you a certain competency. You must try to spell and use grammar correctly (to the best of your ability). You must provide necessary information (e.g. **username** and **domain name**). You must be able to read instructions, and you must be able to follow instructions. We will treat you with respect and professionalism if you follow these guidelines. We will probably be very annoyed if u tyep liek dis.‌

## I log in frequently but am still receiving inactivity emails, what gives?

To ensure that your logins are logged, log in to [heliohost.org](https://heliohost.org) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Each time you do so your last login date is set to the current time. Your account will then remain active for another 30 days. For more details, review our [Inactivity Policy](accounts/suspension-policy.md#inactivity-policy).

## Why must all posts on HelioNet be in English?

The support staff is fluent and reliable only in English.

## Why does HelioHost crash?

Currently, we are running about 20000 different accounts on one server, Johnny. Sometimes, that's a bit too much for Johnny and some user will abuse resources, both causing the server to crash. We try to fix this as quickly as we can. Since the server and Plesk are handling such a high volume of users, errors are bound to come up. We also try to fix these ASAP. Also, when [djbob](misc/staff/ashoat.md) works on the server, he occasionally screws up, which also causes crashes.

## Why was my account suspended?

Our [Suspension Policy](accounts/suspension-policy.md) provides comprehensive details on why we will suspend accounts.

A few common reasons for account suspensions are: 

- [Terms of Service](hosting/terms.md) violation(s).
- [Account Inactivity](accounts/suspension-policy.md#inactivity-policy). Renew your account [here](http://heliohost.org/renew/).
- [Duplicate Accounts](accounts/suspension-policy.md#duplicate-accounts). The limit is 1 account per human being.
- Exceeding the [Account Storage](accounts/suspension-policy.md#account-storage-limits) limits. On Johnny and Tommy, we offer 1000 MB of free web space. There are also paid options available for [increased account storage](accounts/donation-increase-storage.md) and a range of [VPS Plans](https://heliohost.org/vps/).
- Exceeding the [High Server Usage](accounts/suspension-policy.md#high-server-usage) limits. On Johnny and Tommy, we enforce a memory limit of no more than 100 GB and a CPU limit of 10,000 per day. You can monitor your load numbers on [the load page within your dashboard](https://heliohost.org/dashboard/load/).

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

Login to [heliohost.org](https://heliohost.org) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Each time you do so your last login date is set to the current time. Your account will then remain active for another 30 days. For more details, review our [Inactivity Policy](accounts/suspension-policy.md#inactivity-policy).

## What is a Daily Signup Limit and why is it stopping me from registering?

Each server has a daily limit for sign-ups so that it doesn't crash from all the people wanting to use HelioHost. Free signups on Johnny now reset [every 12 hours](https://helionet.org/index/topic/59660-midnight-and-noon/) at midnight UTC and noon UTC.

## What if I have at least $1 and don't want to wait to sign up?

We offer various [Donor Plans](https://heliohost.org/tommy/), so for a one-time donation of as little as $1 USD, you can open an account any time of day.

## My account was deleted. Can I get my data back?

No. We do not keep backups of your data nor is it our responsibility to, as mentioned in our [Terms of Service](hosting/terms.md). You must backup your own data regularly.  

If you're not sure how to backup your data, please see our [Account Backups](tutorials/plesk/account-backups.md) tutorial page. It contains guidance on creating manual backups which you can download to your local machine, and instructions for setting up scheduled automated backups within Plesk.

## Can I have more than one account?

No. It's [one account per user](accounts/suspension-policy.md#duplicate-accounts). This means that you cannot have more than 1 account, even if you use different email addresses. The limit is **1 account per human being**.

## How do I reset my hosting account to start fresh?

Because wiping an account is destructive, we have to verify your identity before we do so. This is to prevent someone from pretending to be you and deleting all your data.

To request that we reset your account so you can start over, send an email **from the same email address as your hosting account** to `support@heliohost.org` so we can verify your identity and wipe your account. Alternatively, you can make a post on the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) from a forum account with the same email address as your hosting account. If you're not sure what email address is associated with your hosting account, you can check by logging into Plesk and navigating to: **Account > My Profile > General > External email address**

Once your account has been reset, you will receive an email with a link to restart your account. **You will have 7 days to use the link.** If you don't use the link to restart your account within 7 days, you will need to signup for a brand new account.

If you had WSGI Control Access on your account for [Flask](tutorials/flask.md) or [Django](tutorials/django.md) and you want this re-enabled after the reset, you will need to re-request WSGI Control Access after the reset has been completed. By default, account resets will disable WSGI Control Access.

### VPS Rebuilds

Due to certain users abusing our generosity in the past and requesting 50 or so rebuilds in less than a month, we now limit each VPS to **1 free rebuild per month**. 

#### Purchasing Additional VPS Rebuilds

If you need to purchase an additional VPS rebuild, please use the link below to donate $1 USD:

{% embed url="https://www.paypal.com/ncp/payment/6Z88J5KJZJ3RJ" caption="Donate $1 USD for VPS Rebuild" %}

After you have made the donation, please provide your [PayPal Transaction ID](accounts/donation-increase-storage.md#paypal-transaction-id) as part of your VPS rebuild request, so the donation can be verified.

## How do I delete my hosting account?

To delete your HelioHost Plesk account, post a topic in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add).

To delete your HelioNet Forum account, post a topic in the [Contact HelioNet forum](https://helionet.org/index/forum/4-contact-helionet/?do=add).

## How do I change my main domain?

To change the main domain on your HelioHost Plesk account, post a topic in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) and let us know your **username** and **what domain you want as your new main domain**.

As an alternative to changing your main domain, consider using [Parked, Addon, and/or Sub Domains](management/parked-addon-and-sub-domains.md).

## What are the nameservers for HelioHost?

* `ns1.heliohost.org`
* `ns2.heliohost.org`

## Can I PM an administrator for help?

No, do not PM the administrators expecting support unless we explicitly tell you to. Please use the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/) instead. Also, in order for us to provide the best and most efficient support, please provide your **username**, **domain name**, and **server name** along with any requests. If you are sending your support request via email to `support@heliohost.org`, make sure to contact us **from the same email address as your hosting account**.

## The server is slow / Feature XYZ doesn't work / Something's wrong with my account / etc.

Please post the issue in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/) and we will try to solve the problem. Also, in order for us to provide the best and most efficient support, please provide your **username**, **domain name**, **server name**, and any **error messages** you are encountering.

## Can Feature XYZ be installed?

Softaculous returned to Johnny and Tommy servers in [March 2024](https://helionet.org/index/topic/59683-softaculous-has-returned/), making it possible to install the latest version of 459 different software packages with just a single click.

To browse the available options, login to Plesk and select Softaculous from the menu:

![](.gitbook/assets/softaculous_menu_item.png) 

If you need a system-wide feature installed, please post a request in our [Customer Service forum](https://helionet.org/index/forum/45-customer-service/), making sure to provide your **username**, **domain name**, **server name**, and any applicable **version numbers**.

## Can I use SSH?

On hosting accounts, secure shell access (SSH) is disabled for security reasons. 

However, it is possible to run jailed shell commands using Plesk's [Scheduled Tasks (cron jobs)](tutorials/plesk/cron-jobs.md) feature. 

If you require SSH access, it is only available on the [VPS Plans](https://heliohost.org/vps/).

## Does Heliohost support sockets? Which ports are open?

Both our [Tommy](servers/virtual/tommy.md) and [Johnny](servers/virtual/johnny.md) servers have zero inbound ports available to be opened. All ports that are currently open already have services listening. 

If you need a port opened, you'll need to get one of our [VPS Plans](https://heliohost.org/vps/), and you will then have all 65535 ports available to open or close as you want.

## Are directory indexes enabled?

As far as we are aware, it's not currently possible to enable directory indexing (listing). However, it is something we plan on changing eventually because a lot of people like it (even though it's a security vulnerability). 

There is no estimated timeframe as to when this functionality may be implemented, since there are many other higher-priority projects to be completed first.

If directory indexes are enabled in the future, an announcement will be posted in the HelioNet [News](https://helionet.org/index/forum/1-news/) section, as well as elsewhere on our site and our social media.

## Your hosting SUCKS! So do YOU!!!

Please see [this](http://helionet.org/index/topic/4723-suspended/page__p__46231#entry46231).

## I still have a question about HelioHost.

Post in the [Questions forum](https://helionet.org/index/forum/48-questions/) and we'll try to help you the best we can.