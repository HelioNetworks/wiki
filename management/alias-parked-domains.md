# Alias Domains / Parked Domains

Each HelioHost account can have up to 10 domains in total (including [addon domains](addon-domains.md), [subdomains](subdomains.md), and aliases (parked domains)), for free. If you need more than 10 domains, they can be added for a donation.

Users cannot yet manage domains on their account themselves. We plan to add this feature in the future, but [there is no ETA for when it may be implemented](../hosting/repair-times.md). 

In the meantime, HelioHost staff will be happy to help you manage your alias domains.

## What is an Alias?

It is like a pet name of a person. You can call that person with their real name (main domain) or with a pet name (alias). Both names point to a _single person_. Likewise, You can use two or more domain names for your single web page.

## How does it differ from Addon Domain?

The difference between addon domains and aliases is simply this:

- With addon domains, you build a completely separate site.
- With an alias, it is already built, you just are giving it another domain for the site it is parked on.

## How Aliases can be helpful

Well, let's say your main domain goes down due to the domain host having problems. If this happens, you can reach your site from your alias. That is very convenient, if you ask me!

## How can I create an Alias?

To create an alias, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **alias** (domain you want to park), **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)
3. The **destination for the alias** (the existing domain on your account you want to duplicate)

The alias will be configured to reflect your `httpdocs` directory. If you want it to reflect a different directory, you will need to request an [Addon Domain](#Addon-Domains) instead.

## Aliases Attached to Custom Domains

## Nameservers

You will need to point the alias on your custom domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

## DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) for the alias to your custom domain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

## What do I do now?

{% hint style="info" %}
Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your alias to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).  
{% endhint %}

## Checking DNS for Aliases Attached to Custom Domains

Full DNS propagation can take up to 24 - 48 hours globally in some cases. To check that your DNS is properly configured, go to [https://dnschecker.org](https://dnschecker.org/). Select the type of record you want to check (NS record, A record, or AAAA record), and type in your alias.

## Deleting Alias Domains

## How can I delete an Addon Domain?

To request deletion of an alias domain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **alias domain** you want deleted.