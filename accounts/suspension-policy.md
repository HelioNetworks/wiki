# Suspension Policy

There are a number of reasons why we might suspend you. To keep your account active, and avoid suspension, make sure you follow our simple requirements we have.

## Inactivity Policy

To ensure that old, unused HelioHost accounts are not filling up our server with useless data, we have an inactivity policy in place which will suspend you if you do not login to cPanel at least once every 30 days. If your account is to be suspended due to inactivity, you will receive an email warning you that you must login to cPanel soon. You will also receive an email when your account is suspended, and is queued for deletion.

To activate a suspended account which was suspended due to inactivity, go to [http://www.heliohost.org/home/support/scripts/renew](http://www.heliohost.org/home/support/scripts/renew).

If you receive an inactivity email even though you have logged into cPanel recently, then you might be logged into cPanel using a faulty URL. When you login to cPanel, ensure that the URL ends in `.phpcp` or `.php` , NOT `.html` .

## Terms of Service

At HelioHost, we have a Terms of Service which all members are required to follow. If you break the Terms of Service, then you will be permanently suspended.

[Click here to look at the Terms of Service](../hosting/terms.md) which you agree to when you signup.

## High Server Usage

To ensure that every site on HelioHost is not slowed down by just one site hogging the server resources, we enforce a High Server Usage policy on all websites, which ensures that no website increases the server load in a massive scale. If your site is found increasing the server load by 20.00 or more, then your account will be permanently suspended.

HelioHost runs a auto-suspension script that monitors all processes. If any of your processes use more than 20% CPU \(calculated over 10 seconds\) or 20% memory, cPanel processes exempt, our script will automatically detect those processes and suspend your account.

## Cron Job Limit

To ensure that your site does not increase the server load significantly, we have a cron job limit which states that you can only run 2 jobs per day. Remember that it is two runs \(eg. One cron job, Runs twice a day\) **not** two separate jobs \(eg. Two cron jobs, Each runs twenty times a day\). If you are caught going over this limit, your account will be permanently suspended.

## Duplicate Accounts

On HelioHost, each person/user is only allowed one account on HelioHost. If you require more than one website, then many features of another HelioHost account are already possible with your current account - read up on [Parked, Addon and Sub Domains](../management/parked-addon-and-sub-domains.md) for more information on how to make multiple websites on one account.

If you are caught with two or more accounts, you will be asked which one\(s\) you would like to be deleted, and if you do not reply we will permanently suspend all of them.

## Further Information

If you have been suspended for something, and the renew script doesn't work, and you're not sure why or what for, then please don't hesitate to post in the [customer service forum](https://www.helionet.org/index/forum/45-customer-service/) on [HelioNet](../hosting/helionet.md).

