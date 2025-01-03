# Setting Up Email on a VPS running Hestia Control Panel

This tutorial will help you set up SMTP email service using the Hestia Control Panel installed on your HelioHost VPS.

## Getting Started

You will need: 
* A [HelioHost VPS](https://heliohost.org/vps/)
* Hestia Control Panel installed on your VPS
  * Your VPS will come with Hestia preinstalled if you requested this during signup
  * **Note:** Control panels like Hestia can only be installed on a fresh operating system with no other software or configurations already in place
  * If you do not have a freshly installed OS, you can:
    * Request a [VPS rebuild](../../faq.md#vps-rebuilds) and ask for Hestia to be preinstalled
    * Request a [VPS rebuild](../../faq.md#vps-rebuilds) and install Hestia yourself. There is a helpful tutorial [here](https://hestiacp.com/docs/introduction/getting-started.html)
* A domain you want to use for email

## Log In to Hestia

In your web browser, navigate to the `Domain` web address provided in your welcome email (`vps##.heliohost.us`) and log in to your Hestia Control Panel.

## Check Firewall Rules

First, we will make sure the necessary ports are open:
* Click on the Settings gear wheel icon at the top right
* Click on the `Firewall` button

![](../../.gitbook/assets/vps-hestia-email-1-firewall.png)

## Confirm Open Ports

Doublecheck that the following ports are set to `Accept` connections from IP Address `0.0.0.0/0` (which means it allows all IPs):
* Hestia: 8083
* SMTP: 25, 465, 587
* Web: 80, 443

![](../../.gitbook/assets/vps-hestia-email-2-ports.png)

{% hint style="info" %}
If you already have a domain set up inside Hestia that you want to add mail service to, you can skip right to the [Add Mail Domain](#add-mail-domain) section.
{% endhint %}

## Create a Standard User Account

The system administrator account we used to log in to Hestia has increased privileges. To prevent potential security risks, we will create an account with fewer permissions that will still enable us to set mail service up.

* Click on the `User` tab
* Click on the `Add User` button
* Fill in the form fields
* Set the `Role` field to `User`
* Set the `Package` to `Default`
* Click on the `Save` button at the top right side of the page
* You should see a message that says: "User `username` has been created successfully. / Log in as `username`"
* Click on the link that says: "Log in as `username`"

<!-- We can use the same screenshot from another Hestia tutorial -->
![](../../.gitbook/assets/vps-tutorial-wp-hestia-1-login-user.png)

### Add Web Domain

* Click on the `Web` tab
* Click on the `Add Web Domain` button
* Enter your domain or subdomain (e.g. `domain.com`, without the leading `http://` or `https://`)
* Select the `Mail Support` option to enable email for this domain
* Click on the `Save` button at the top right side of the page
* You should see a message that says: "Domain `domain.com` has been created successfully."

<!-- We can use the same screenshot from another Hestia tutorial -->
![](../../.gitbook/assets/vps-tutorial-wp-hestia-2-domain-created.png)

## Add Mail Domain

Click on the `Mail` tab 

If your domain is not listed:
* Click on the `Add Mail Domain` button
* Set the `Domain` field to `domain.com` (without the leading `http://` or `https://`)
* Select `DKIM Support`
* Click on the `Save` button at the top right side of the page
* You should see a message that says "Mail domain `domain.com` has been created successfully."
* Click on the `Mail` tab again
* Click on the small `DNS Records` button next to your domain

If your domain is listed: 
  * Click on the small `DNS Records` button next to your domain

## View DNS Records

Hestia Control Panel automatically creates the necessary mail records for our SMTP server. To view your mail DNS records, select the `Mail` tab and click on the small `DNS Records` button next to your domain. 

![](../../.gitbook/assets/vps-hestia-email-3-dns-records.png)

{% hint style="info" %}
You will need to login to your domain registrar account and add all the records shown to the DNS management section.
{% endhint %}

## Enable SSL

We recommend that you enable SSL for your mail domain. Inside Hestia: 
* Click on the `Web` tab
* Click on the small `Edit Domain` button next to your domain

<!-- We can use the same screenshot from another Hestia tutorial -->
![](../../.gitbook/assets/vps-tutorial-wp-hestia-3-edit-domain.png)

* Select your preferred SSL settings, and click on the `Save` button at the top right side of the page
* You should see a message that says `Changes have been saved.`

## Update Domain Registrar

Before proceeding, make sure you have logged in to your domain registrar account and added the values shown in Hestia to the DNS management section.

### Namecheap

If you use Namecheap as your domain registrar, the below guidance should help you add the necessary details to their DNS management section.

Login to your Namecheap account, find your domain in the list and click on the `Manage` button:

![](../../.gitbook/assets/vps-hestia-email-4-namecheap-manage-dns.png)

Click on the `Advanced DNS` tab

![](../../.gitbook/assets/vps-hestia-email-5-namecheap-advanced-dns.png)

Enter the DNS record values provided in Hestia into your Namecheap dashboard for the two `A` records, four `TXT` records, and the one `MX` record:

![](../../.gitbook/assets/vps-hestia-email-6-namecheap-a-txt-mx-records.png)

## Add Mail User Accounts

After adding all the DNS records to your domain registrar site, return to Hestia. Make sure you are logged in as the user who set up the mail domain. 
* Click on the `Mail` tab
* Click on the small `Add Mail Account` button next to your domain

![](../../.gitbook/assets/vps-hestia-email-7-add-mail-account.png)

## Add Email Account

* Enter the `Account` name and `Password` for the email account
  * The value you enter for `Account` will be the first part (before the `@domain.com`) of the email address

![](../../.gitbook/assets/vps-hestia-email-8-add-email-address.png)

* Click on the `Save` button
* You should see a message that says: "Mail account `name@domain.com` has been created successfully."

## Check Webmail

You can access your webmail at `webmail.domain.com`

### Troubleshooting

When trying to access your webmail link, if you receive an error message that says: `Oops... something went wrong! An internal error has occurred. Your request cannot be processed at this time. For administrators: Please check the application and/or server error logs for more information.`, follow the steps below.

![](../../.gitbook/assets/vps-hestia-email-9-oops-error.png)

#### Check Ownership and Permissions

To check the owner and permissions on the files in the `roundcube` folder, open a new terminal window and login to your VPS. 

Navigate to `/etc/roundcube/` and list the contents of the folder:
```text
sudo ls -al
```

You should see:  
```text
total 92
drwxr-x--x   3 hestiamail hestiamail  4096 Jul 11 23:54 .
drwxr-xr-x 120 root       root       12288 Jul 11 23:47 ..
-rw-r-----   1 hestiamail hestiamail  3719 Jun 26 21:16 config.inc.php
-rw-r-----   1 hestiamail hestiamail 64583 Jun 26 21:16 defaults.inc.php
-rw-r-----   1 hestiamail hestiamail  2760 Jun 26 21:16 mimetypes.php
drwxr-x--x   5 hestiamail hestiamail  4096 Jun 26 21:16 plugins
```

#### Update Ownership and Permissions

If your files have a different owner or different permissions, we can follow the suggestion in this [this Hestia support post](https://forum.hestiacp.com/t/after-installing-hestia-1-8-11-in-ubuntu-22-04-the-roundcube-cannot-be-opened/12114/2).

Change file ownership:
```text
sudo chown -R hestiamail:hestiamail /etc/roundcube/
```

Change file permissions:
```text
sudo find /etc/roundcube/ -type f -iname "*php" -exec chmod 640 {} \;
```

#### Check Webmail Again

You should now be able to open `webmail.domain.com` and login with `name@domain.com` and the password you set up.

## Check Email Trust Score

You can test the likelihood of your emails being received by using GMass's free SMTP Test Tool and a free test email address from mail-tester. 

In a new browser tab, visit [mail-tester.com](https://www.mail-tester.com/) and make a note of the `@mail-tester.com` email address. 

In a second new browser tab, visit [gmass.co/smtp-test](https://www.gmass.co/smtp-test/). In the `To email address` field, use the email address from mail-tester. Fill in the rest of your credentials, and click the `Test it` button. 

Once the test email has been sent, return to the mail-tester tab and click on the `Then check your score` button. You will then get an analysis of your email settings, and suggestions on what to fix if any misconfigurations are detected.

## Further Support

If after following the above steps, you are unable to view your webmail, aren't sure how to fix a mail-tester score of less than 10/10 or have any other issues, please post a topic in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add). Please make sure you provide your **VPS number** and details about the problem, such as the mail-tester report, or any **error message(s)** received.