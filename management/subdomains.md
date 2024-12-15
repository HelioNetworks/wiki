# Subdomains

Each HelioHost account can have up to 10 domains in total (including [addon domains](addon-domains.md), subdomains, and [aliases (parked domains)](alias-parked-domains)), for free. If you need more than 10 domains, they can be added for a donation.

Users cannot yet manage domains on their account themselves. We plan to add this feature in the future, but [there is no ETA for when it may be implemented](../hosting/repair-times.md). 

In the meantime, HelioHost staff will be happy to help you manage your subdomains.

## What is a subdomain

A subdomain is like an "attachment" to a current domain that reflects a normal directory. For instance, if you didn't want to host your blog in a subdirectory such as `mydomain.helioho.st/blog/` you could make a subdomain `blog.mydomain.helioho.st` instead. For the speed and reliability of the server, we recommend using a subdirectory rather than a subdomain though as having too many domains on a server causes the uptime to drop for everyone. For SEO performance it's best to use a subdirectory as well.

## How can I create a subdomain?

To create a subdomain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **subdomain** you want added
3. The **full domain** you want the subdomain to be attached to, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)

The subdomain will be configured to display the files located in the matching directory. Therefore, if your document root was `/subdomain.maindomain.helioho.st/` your new subdomain will serve the files located in that directory.

## Subdomains Attached to Custom Domains

## Nameservers

You will need to point your custom subdomain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

## DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) to your custom subdomain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

## What do I do now?

{% hint style="info" %}  
Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your subdomain to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).  
{% endhint %}

## Checking DNS for Subdomains Attached to Custom Domains

Full DNS propagation can take up to 24 - 48 hours globally in some cases. To check that your DNS is properly configured, go to [https://dnschecker.org](https://dnschecker.org/). Select the type of record you want to check (NS record, A record, or AAAA record), and type in your custom subdomain.

## Deleting Subdomains

## Backup Your Account

{% hint style="warning" %}  
There is a risk of data loss when subdomains are deleted. We strongly recommend you [create an account backup](../tutorials/plesk/account-backups.md#making-your-own-manual-account-backup) before requesting to delete a subdomain. As mentioned in our [Terms of Service](../hosting/terms.md), it is not HelioHost's responsibility to keep backups of your data.  
{% endhint %}  

## How can I delete an Addon Domain?

To request deletion of a subdomain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **subdomain** you want deleted.