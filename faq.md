# FAQ

## Your homepage says "Professional-Grade Hosting", but your support sucks / isn't helping me / is run by a number of volunteers, what gives?‌

There is a difference between "Professional-Grade Hosting" and "Professional-Grade Customer Support". Most people are used to having dedicated customer support staff that will answer every little question; this comes standard with paid hosting. However, we don't do that here. Among the five of us, we have the collective knowledge and technical expertise of any other support staff, but in order for us to help you, we expect from you a certain competency. You must try to spell and use grammar correctly \(to the best of your ability\). You must provide necessary information \(e.g. **username** and **domain name**\). You must be able to read instructions, and you must be able to follow instructions. We will treat you with respect and professionalism if you follow these guidelines. We will probably be very annoyed if u tyep liek dis.‌

## I log in frequently but am still receiving inactivity emails, what gives?

To ensure that your logins are logged, login to [heliohost.org](https://heliohost.org) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Each time you do so your last login date is set to the current time. Your account will then remain active for another 30 days. For more details, review our [Inactivity Policy](https://wiki.helionet.org/accounts/suspension-policy#inactivity-policy).

## Why must all posts on HelioNet be in English?

The support staff is fluent and reliable only in English.

## Why does HelioHost crash?

Currently, we are running about 20000 different accounts on one server, Johnny. Sometimes, that's a bit too much for Johnny and some user will abuse resources, both causing the server to crash. We try to fix this as quickly as we can. Since the server and Plesk are handling such a high volume of users, errors are bound to come up. We also try to fix these ASAP. Also, when [djbob](misc/staff/ashoat.md) works on the server, he occasionally screws up, which also causes crashes.

## Why was my account suspended?

Our [Suspension Policy](https://wiki.helionet.org/accounts/suspension-policy) provides comprehensive details on why we will suspend accounts.

A few common reasons for account suspensions are:

- [Terms of Service](hosting/terms.md) violation(s).
- [Account Inactivity](/accounts/suspension-policy.md#inactivity-policy). Renew your account [here](http://heliohost.org/renew/).
- [Duplicate Accounts](https://wiki.helionet.org/accounts/suspension-policy#duplicate-accounts). The limit is 1 account per human being.
- Exceeding the [Cron Job Limit](https://wiki.helionet.org/accounts/suspension-policy#cron-job-limit).

It is also possible that this was an error in our system. If you suspect that this is the case, report the error in a new post [here](https://helionet.org/index/forum/81-suspended-and-queued-accounts/), making sure to provide your **username**.

## Why does my new subdomain show a "Queued" page?

{% hint style="info" %}
All domain and subdomain changes take **up to 2 hours** to go into effect as they require an Apache restart. 
{% endhint %}

During the first 2 hours, seeing the queued page is normal and only means the change hasn't taken effect yet. If it's been longer than **a full 2 hours**, try [clearing your browser cache](https://wiki.helionet.org/misc/clear-your-cache).

## Why can't I log in?

{% hint style="info" %}
If you just registered, please wait **up to 2 hours** for your Plesk account to become fully active.
{% endhint %}

If it has been longer than **a full 2 hours** since you registered and you still see an `Account Queued` page, try [clearing your browser cache](https://wiki.helionet.org/misc/clear-your-cache). If you are still experiencing problems, make sure you are entering your username in all lowercase letters, i.e. "wizard", not "Wizard" or "WIZARD".

## How do I keep my account active / prevent being suspended?

Login to [heliohost.org](https://heliohost.org) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Each time you do so your last login date is set to the current time. Your account will then remain active for another 30 days. For more details, review our [Inactivity Policy](https://wiki.helionet.org/accounts/suspension-policy#inactivity-policy).

## What is a Daily Signup Limit and why is it stopping me from registering?

Each server has a daily limit for sign-ups so that it doesn't crash from all the people wanting to use HelioHost. Free signups on Johnny now reset [every 12 hours](https://helionet.org/index/topic/59660-midnight-and-noon/) at midnight UTC and noon UTC.

## What if I have at least $1 and don't want to wait to sign up?

We offer various [Donor Plans](https://heliohost.org/tommy/), so for a one-time donation of as little as $1 USD, you can open an account any time of day.

## My account was deleted. Can I get my data back?

No. We do not keep backups of your data nor is it our responsibility to, as mentioned in our [Terms of Service](hosting/terms.md). You must backup your own data regularly.  

If you're not sure how to backup your data, please see our tutorials on [Making Your Own Manual Account Backup](/tutorials/plesk/account-backups.md#making-your-own-manual-account-backup) and [Scheduling Automated Account Backups](/tutorials/plesk/account-backups.md#scheduling-automated-account-backups).  

However, if your HelioHost Plesk account was deleted due to inactivity, feel free to create a new account.

## Can I have more than one account?

No. It's [one account per user](/accounts/suspension-policy.md#duplicate-accounts). This means that you cannot have more than 1 account, even if you use different email addresses. The limit is **1 account per human being**.

## How do I reset my hosting account to start fresh?

Because wiping an account is destructive, we have to verify your identity before we do so. This is to prevent someone from pretending to be you and deleting all your data.

To request that we reset your account so you can start over, send an email **from the same email address as your hosting account** to `support@heliohost.org` so we can verify your identity and wipe your account. Alternatively, you can make a post on the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) from a forum account with the same email address as your hosting account.

Once your account has been reset, you will receive an email with a link to restart your account. **You will have 7 days to use the link.** If you don't use the link to restart your account within 7 days, you will need to signup for a brand new account.

### VPS Rebuilds

Due to certain users abusing our generosity in the past and requesting 50 or so rebuilds in less than a month, we now limit each VPS to **1 free rebuild per month**. After that, you can purchase additional rebuilds for $1 USD each.

## How do I delete my hosting account?

To delete your HelioHost Plesk account, post a topic in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add).

To delete your HelioNet Forum account, post a topic in the [Contact HelioNet forum](https://helionet.org/index/forum/4-contact-helionet/?do=add).

## How do I change my main domain?

To change the main domain on your HelioHost Plesk account, post a topic in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add) and let us know your **username** and **what domain you want added**.

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

On hosting accounts, SSH access is disabled for security reasons.

If you require SSH access, it is only available on the [VPS Plans](https://heliohost.org/vps/).

## Does Heliohost support sockets? Which ports are open?

Both our [Tommy](/servers/virtual/tommy.md) and [Johnny](/servers/virtual/johnny.md) servers have zero inbound ports available to be opened. All ports that are currently open already have services listening. 

If you need a port opened, you'll need to get one of our [VPS Plans](https://heliohost.org/vps/), and you will then have all 65535 ports available to open or close as you want.

## Your hosting SUCKS! So do YOU!!!

Please see [this](http://helionet.org/index/topic/4723-suspended/page__p__46231#entry46231).

## I still have a question about HelioHost.

Post in the [Questions forum](https://helionet.org/index/forum/48-questions/) and we'll try to help you the best we can.
