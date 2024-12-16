# Changing Your Main Domain

Each HelioHost account can have up to 10 domains in total (including [addon domains](addon-domains.md), [subdomains](subdomains.md), and [aliases (parked domains)](alias-parked-domains)), for free. If you need more than 10 domains, they can be added for a donation.

Users cannot yet change the main domain on their account themselves. We plan to add this feature in the future, but [there is no ETA for when it may be implemented](../hosting/repair-times.md). 

In the meantime, HelioHost staff will be happy to change your main domain for you.

## Before Changing Your Main Domain

Before requesting to change your main domain, read up on [Parked (Alias)](alias-parked-domains.md), [Addon](addon-domains.md), and [Subdomains](subdomains.md) as a useful alternative to changing your main domain. You can host up to 10 domains on your one hosting account (with the possibility of adding more for a donation), so most of the time it's pointless to change your main domain when you can simply add the new domain as an alias.

## Make an Account Backup

{% hint style="warning" %}  
There is a risk of data loss when main domains are changed. We strongly recommend you [create an account backup](../tutorials/plesk/account-backups.md#making-your-own-manual-account-backup) before requesting to change your main domain.  

As mentioned in our [Terms of Service](../hosting/terms.md), it is not HelioHost's responsibility to keep backups of your data.  
{% endhint %}

## Submit a Request to Change Your Main Domain

{% hint style="warning" %}  
Make sure the main domain you're changing to isn't already added to Plesk as an Alias or an Addon domain. Otherwise, the main domain change will fail.  
{% endhint %}

To change your main domain (the location of where your visitors will navigate to), submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **full domain name** you want as your main domain, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)

### Custom Domains

### Nameservers

You will need to point your custom domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

### DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) to your custom domain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

### Next Steps

{% hint style="info" %}  
Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your new main domain to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).  
{% endhint %}