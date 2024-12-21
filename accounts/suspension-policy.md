# Suspension Policy

There are a number of reasons why we might suspend you. To keep your account active, and avoid suspension, make sure you follow our simple requirements.

## Terms of Service

Before users can create a HelioHost account, they must confirm they agree to follow the [Terms of Service](../hosting/terms.md). 

## Three-Strike Policy

At HelioHost, we strive to create a friendly and educational online experience for all our users. As part of that commitment, we prefer to use a three-strike policy against accounts that violate our [Terms of Service](../hosting/terms.md).

This three-strike policy provides offenders with a series of disciplinary actions that offer them multiple chances to change their behavior. Everyone makes mistakes sometimes, so this policy allows users to learn from their mistakes and change their ways. 

We are happy to offer advice to users whose accounts are suspended for high server usage, who are unaware that they can manage multiple sites from a single account, or who may be otherwise unsure of how to correct their [Terms of Service](../hosting/terms.md) violation(s). When we unsuspend accounts, we expect users to make a genuine effort to stop breaking our rules.

Users who repeatedly break our [Terms of Service](../hosting/terms.md) or who refuse to correct their behavior will have their accounts suspended permanently.

## Immediate Account Suspension

Although we prefer to approach [Terms of Service](../hosting/terms.md) violations using our three-strike policy, some offenses may result in immediate permanent account suspension without prior warning. Rudeness or disrespect to staff, lying or other dishonesty to staff, harassment of staff, abuse of the hosting service itself, such as creating phishing sites or promoting other illegal activity, or other offenses to be determined at our sole discretion will result in immediate permanent account suspension.

## High Server Usage

To ensure that every site on HelioHost is not slowed down by just one account hogging the server resources, we enforce a High Server Usage policy on all shared hosting servers, which ensures that no website increases the server load on a massive scale.

### Account Load Limits

We enforce a memory limit of no more than 100 GB per day and a limit of 10,000 CPU usage per day.
* On the [Johnny](../servers/virtual/johnny.md) and [Tommy](../servers/virtual/tommy.md) servers, if you exceed these limits, your account will be suspended.
* On the [Morty](../servers/virtual/morty.md) server, if you exceed these limits, we will charge you for overages.

{% hint style="warning" %}  
We strongly recommend that you proactively monitor your account load numbers on [the load page within your dashboard](https://heliohost.org/dashboard/load/).  
{% endhint %}

### Understanding Memory and CPU

Memory is short-term computer storage, often called RAM (random access memory).

CPU is the brain of a computer that processes instructions and performs calculations, also known as the Central Processing Unit.

### How Account Load is Calculated

On [the load page within your dashboard](https://heliohost.org/dashboard/load/), account load totals are calculated by taking a sample once every 60 seconds. So, for instance, if you use 1 MB of memory constantly for the full 24 hours your total would be 1.4 GB at the end of the day. The CPU unit is 1% of the total speed of a CPU core, so if you used 1% of the core constantly for the entire day your total would be 1440 at the end of the day. 

If you have any questions, or need help reducing your account load, don't hesitate to open a support ticket on the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add). Make sure to provide: 
1) Your **username**
2) Your **domain name**
3) Your  **server name**
4) Details about the technology being used on your site ([WordPress](../misc/wordpress.md), [Node.js](../features/node.js.md), etc.)

### Cron Jobs / Scheduled Tasks

In Plesk, cron jobs are called [Scheduled Tasks](../tutorials/plesk/cron-jobs.md). There is no limit on the number of cron jobs you can run, but they count towards your total account load. This means that running too many cron jobs or having one cron job run too frequently can increase your risk of getting suspended under the [High Server Usage](/accounts/suspension-policy.md#high-server-usage) policy. For example, sometimes people start a cron job to run every 1 minute and then get suspended for high load pretty quickly because of it. You can monitor your account load numbers on [the load page within your dashboard](https://heliohost.org/dashboard/load/).

## Account Storage Limits

On [Johnny](../servers/virtual/johnny.md), [Tommy](../servers/virtual/tommy.md), and [Morty](../servers/virtual/morty.md), we offer 1000 MB of web space. This figure combines your stored files (including [account backups](../tutorials/plesk/account-backups.md) and [error logs](../tutorials/plesk/view-error-logs.md)) and your databases. This limit should not be a problem to the great majority of hosting users. 

We offer paid storage upgrade options:
- Make a one-time [donation to increase your account storage](donation-increase-storage.md) to a maximum of 6000 MB total.
- Sign up for a [VPS plan](https://heliohost.org/vps/) offering storage options ranging from 50 GB to 300 GB total, and get a 10% discount when you pay for 6 months upfront.

## Duplicate Accounts

Each person/user is only allowed one account on HelioHost. Even if you use different email addresses. The limit is **1 account per human being**. 

### Signup page mentions 1 account per person

Below the server choices on the signup page, users are shown a warning that says, **"You may only have one account"**: 

![](../.gitbook/assets/mutiple-acct-warning-1.png)

### Terms of Service page mentions 1 account per person

The first item of the [Terms of Service](../hosting/terms.md), which all users must agree to before creating an account, says, **"Each person is allowed to have one account"**:

![](../.gitbook/assets/mutiple-acct-warning-2.png)

If you require more than one website, then many features of another HelioHost account are already possible with your current account. Read up on [Parked (Alias)](alias-parked-domains.md), [Addon](addon-domains.md), and [Subdomains](subdomains.md) for more information on how to make multiple websites on one account.

If you are caught with two or more accounts, you will be asked which one(s) you would like to be deleted, and if you do not reply we will permanently suspend all of them.

### Managing Accounts on Behalf of Others

Managing someone else's account on their behalf is considered the same as having 2 accounts and will subject you to suspension unless **approved ahead of time** by an admin.

## Inactivity Policy

To ensure that old, unused HelioHost accounts are not filling up our server with useless data, we have an inactivity policy in place on the [Johnny](../servers/virtual/johnny.md) and [Tommy](../servers/virtual/tommy.md) servers. Your account will be suspended if you do not log in to [heliohost.org](https://heliohost.org/) or [heliohost.org/login](https://heliohost.org/login/) at least once every 30 days. Each time you log in, your last login date is set to the current time, so your account will then remain active for another 30 days. There is no such login requirement on the [Morty](../servers/virtual/morty.md) server.

If your Johnny or Tommy account is to be suspended due to inactivity, you will receive an email warning you that you must log in soon at 28 days. You will also receive another email when your website is taken offline at 30 days.

To activate a Johnny or Tommy account that was suspended due to inactivity, go to [heliohost.org/renew](http://heliohost.org/renew/)

{% hint style="info" %}
Account renewals take **up to 2 hours** to go into effect because they require an Apache restart. If it has been longer than **a full 2 hours** since you renewed your account, please make sure you [clear your browser cache](../misc/clear-your-cache.md).
{% endhint %}

If you receive an inactivity email for your Johnny or Tommy account even though you have logged into Plesk recently, then you might be logged into Plesk using a faulty URL. To ensure that your logins are logged, log in at [heliohost.org](https://heliohost.org/) or [heliohost.org/login](https://heliohost.org/login/) at least once a month. Other login methods are not supported.

## Further Information

If you have been suspended for something and you're not sure why or what for, or the renew script doesn't work, please don't hesitate to post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/). To enable us to offer the best and most efficient support, make sure you provide:
1) Your **username**
2) Your **domain name**
3) Your **server name**