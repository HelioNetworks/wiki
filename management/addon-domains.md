# Addon Domains

Each HelioHost account can have up to 10 domains in total (including addon domains, [subdomains](subdomains.md), and [aliases (parked domains)](alias-parked-domains)), for free. If you need more than 10 domains, they can be added for a donation.

Users cannot yet manage domains on their account themselves. We plan to add this feature in the future, but [there is no ETA for when it may be implemented](../hosting/repair-times.md). 

In the meantime, HelioHost staff will be happy to help you manage your addon domains.

## What is an Addon Domain?

An addon domain is a domain which reflects the contents of a folder in your Plesk File Manager.

## How can I create an Addon Domain?

To create an addon domain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **full addon domain** name you want, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)

By default the addon domain will be located in your home folder with a name that matches the domain you requested. For instance, if you requested the domain `mydomain.helioho.st` then the default folder would be `/mydomain.helioho.st/`

## Custom Addon Domains

## Nameservers

You will need to point your custom domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

## DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) to your custom domain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

## What do I do now?

{% hint style="info" %}  
Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your addon domain to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).  
{% endhint %}

## Checking Custom Domain DNS

Full DNS propagation can take up to 24 - 48 hours globally in some cases. To check that your DNS is properly configured, go to [https://dnschecker.org](https://dnschecker.org/). Select the type of record you want to check (NS record, A record, or AAAA record), and type in your custom domain.

## Deleting Addon Domains

## Backup Your Account

{% hint style="warning" %}  
There is a risk of data loss when addon domains are deleted. We strongly recommend you [create an account backup](../tutorials/plesk/account-backups.md#making-your-own-manual-account-backup) before requesting to delete an addon domain. As mentioned in our [Terms of Service](../hosting/terms.md), it is not HelioHost's responsibility to keep backups of your data.  
{% endhint %}

## How can I delete an Addon Domain?

To request deletion of an addon domain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **addon domain** you want deleted.