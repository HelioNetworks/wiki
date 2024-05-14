# Suspension Policy

There are a number of reasons why we might suspend you. To keep your account active, and avoid suspension, make sure you follow our simple requirements.

## Inactivity Policy

To ensure that old, unused HelioHost accounts are not filling up our server with useless data, we have an inactivity policy in place which will suspend you if you do not log in to [heliohost.org](https://heliohost.org/) or [heliohost.org/login](https://heliohost.org/login/) at least once every 30 days. Each time you log in, your last login date is set to the current time, so your account will then remain active for another 30 days.

If your account is to be suspended due to inactivity, you will receive an email warning you that you must log in soon at 28 days. You will also receive another email when your website is taken offline at 30 days.

To activate a suspended account which was suspended due to inactivity, go to [heliohost.org/renew](http://heliohost.org/renew/)

If you receive an inactivity email even though you have logged into Plesk recently, then you might be logged into Plesk using a faulty URL. To ensure that your logins are logged, log in at [heliohost.org](https://heliohost.org/) or [heliohost.org/login](https://heliohost.org/login/) at least once a month.

## Terms of Service

At HelioHost, we have a Terms of Service which all members are required to follow. If you break the Terms of Service, then you will be permanently suspended.

[Click here to look at the Terms of Service](../hosting/terms.md) which you agree to when you sign up.

## High Server Usage

To ensure that every site on HelioHost is not slowed down by just one site hogging the server resources, we enforce a High Server Usage policy on all websites, which ensures that no website increases the server load on a massive scale. On Johnny and Tommy, we enforce a memory limit of no more than 100 GB and a CPU limit of 10,000 per day. If you exceed those amounts you will get suspended. You can monitor your load numbers on [the load page within your dashboard](https://heliohost.org/dashboard/load/).

## Cron Jobs / Scheduled Tasks

<!-- Note: Variations of the term 'cron job', including 'cronjob', 'cron jobs', and 'cronjobs' have been used in this document to enhance discoverability in Wiki search queries.  -->

In Plesk, cron jobs are called [Scheduled Tasks](../tutorials/plesk/cron-jobs.md). There is no limit on the number of cron jobs you can run, but they count towards your total account load. This means that running too many cronjobs or having one cron job run too frequently can increase your risk of getting suspended under the [High Server Usage](/accounts/suspension-policy.md#high-server-usage) policy. For example, sometimes people start a cronjob to run every 1 minute and then get suspended for high load pretty quickly because of it. You can monitor your account load numbers on [the load page within your dashboard](https://heliohost.org/dashboard/load/).

## Duplicate Accounts

Each person/user is only allowed one account on HelioHost. Even if you use different email addresses. The limit is 1 account per human being. If you require more than one website, then many features of another HelioHost account are already possible with your current account. Read up on [Parked, Addon and Sub Domains](../management/parked-addon-and-sub-domains.md) for more information on how to make multiple websites on one account.

If you are caught with two or more accounts, you will be asked which one(s) you would like to be deleted, and if you do not reply we will permanently suspend all of them.

## Further Information

If you have been suspended for something and you're not sure why or what for, or the renew script doesn't work, please don't hesitate to post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/), making sure to provide your **username**, **domain name**, and **server name** up front so we can provide you with the best and most efficient support.
