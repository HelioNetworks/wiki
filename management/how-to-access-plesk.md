# How to Access Plesk

## What is Plesk?

Plesk is a control panel that lets you easily manage your websites, applications, and other aspects of your hosting account. 
Plesk offers a built-in File Manager, [Email](../features/unlimited-email-accounts.md), [MySQL Databases](../management/mysql.md), the [Softaculous](../features/softaculous.md) auto-installer service that enables you to download CMS, Forum, or Blog software, and more.

## How to Access Plesk

### Access over HTTPS (Port 8443)

The usual way to access your Plesk control panel is over HTTPS (Hypertext Transfer Protocol Secure). Plesk uses Port 8443 for this. 

To access your Plesk control panel, navigate to [https://heliohost.org/login](https://heliohost.org/login/) or [https://heliohost.org](https://heliohost.org/) and enter your account details. 

Using the above links will ensure that your logins are logged, removing the risk of your account being [suspended due to inactivity](../accounts/suspension-policy.md#inactivity-policy).

### Access over HTTP (Port 8880)

If your firewall blocks Port 8443, you can use Port 8880 which is the [port Plesk uses](https://docs.plesk.com/en-US/obsidian/administrator-guide/plesk-administration/ports-used-by-plesk.64950/) for HTTP access.  

After trying to login at [https://heliohost.org/login](https://heliohost.org/login/), simply click the "insecure login" button at the bottom of the page.  

{% hint style="warning" %}
We highly recommend logging in to Plesk securely with encryption enabled. So only use Port 8880 when you absolutely have no other way of connecting.
{% endhint %}

## Troubleshooting

If you cannot login to Plesk, there are a few common reasons:

### New Accounts

{% hint style="info" %}
It can take **up to 2 hours** for your account to be fully active.
{% endhint %}

If you have just created your account, it can take up to 2 hours for your account to be fully active. In the meantime, you may not be able to login to Plesk, and your website URL may display the Plesk default page, the CentOS default page, 404 errors, SSL errors, etc. Please be patient and wait for the full 2 hours before assuming anything is broken.

#### Check Account Activation Status

To check the status of your account and see an approximation of the activation completion time, go to [https://heliohost.org/status](https://heliohost.org/status/).

If after a full 2 hours, you still see a message saying `HelioHost Account Queued`, then please [clear your cache](../misc/clear-your-cache.md).

### Multiple Accounts

On HelioHost, each person/user is only allowed one account. [Multiple accounts will be suspended](../accounts/suspension-policy.md#duplicate-accounts).

### Inactive Accounts

If it has been 30 days or more since your last Plesk login, your account was likely [suspended due to inactivity](../accounts/suspension-policy.md#inactivity-policy).

To activate a suspended account which was suspended due to inactivity, go to [https://heliohost.org/renew](https://heliohost.org/renew/).

## Further Support

If none of the above reasons apply to you and you cannot access Plesk, please create a new post in the [Customer Service forum](https://helionet.org/index/forum/81-suspended-and-queued-accounts/), making sure to provide your **username**, **domain name**, **server name**, and any **error message(s)** received.