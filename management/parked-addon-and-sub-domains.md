# Addon Domains, Subdomains, and Aliases

Addon domains, subdomains, and aliases are vital services that allow you to host multiple websites on your one account. Each HelioHost account can have up to 10 domains for free, and if you need more than 10 domains they can be added for a donation. However, using these services can be confusing, and some problems can occur in the process. But don't worry - this article will help alleviate any confusion.

## Addon Domains

### What is an Addon Domain?

An addon domain is a domain which reflects the contents of a folder in your Plesk File Manager.

### How can I create an Addon Domain?

To create an addon domain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **full addon domain** name you want, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)

By default the addon domain will be located in your home folder with a name that matches the domain you requested. For instance, if you requested the domain `mydomain.helioho.st` then the default folder would be `/mydomain.helioho.st/`

### Custom Addon Domains

### Nameservers

You will need to point your custom domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

### DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) to your custom domain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

### What do I do now?

Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your addon domain to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).

### Checking Custom Domain DNS

Full DNS propagation can take up to 24 - 48 hours globally in some cases. To check that your DNS is properly configured, go to [https://dnschecker.org](https://dnschecker.org/). Select the type of record you want to check (NS record, A record, or AAAA record), and type in your custom domain.

## Subdomains

### What is a subdomain

A subdomain is like an "attachment" to a current domain that reflects a normal directory. For instance, if you didn't want to host your blog in a subdirectory such as `mydomain.helioho.st/blog/` you could make a subdomain `blog.mydomain.helioho.st` instead. For the speed and reliability of the server, we recommend using a subdirectory rather than a subdomain though as having too many domains on a server causes the uptime to drop for everyone. For SEO performance it's best to use a subdirectory as well.

### How can I create a subdomain?

To create a subdomain, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **subdomain** you want added
3. The **full domain** you want the subdomain to be attached to, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)

The subdomain will be configured to display the files located in the matching directory. Therefore, if your document root was `/subdomain.maindomain.helioho.st/` your new subdomain will serve the files located in that directory.

### Subdomains Attached to Custom Domains

### Nameservers

You will need to point your custom subdomain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

### DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) to your custom subdomain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

### What do I do now?

Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your subdomain to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).

### Checking DNS for Subdomains Attached to Custom Domains

Full DNS propagation can take up to 24 - 48 hours globally in some cases. To check that your DNS is properly configured, go to [https://dnschecker.org](https://dnschecker.org/). Select the type of record you want to check (NS record, A record, or AAAA record), and type in your custom subdomain.

## Alias Domains

### What is an Alias?

It is like a pet name of a person. You can call that person with their real name (main domain) or with a pet name (alias). Both names point to a _single person_. Likewise, You can use two or more domain names for your single web page.

### How does it differ from Addon Domain?

The difference between addon domains and aliases is simply this:

- With addon domains, you build a completely separate site.
- With an alias, it is already built, you just are giving it another domain for the site it is parked on.

### How Aliases can be helpful

Well, let's say your main domain goes down due to the domain host having problems. If this happens, you can reach your site from your alias. That is very convenient, if you ask me!

### How can I create an Alias?

To create an alias, submit a request in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and provide the following information:
1. Your hosting account **username**  
2. The **alias (domain you want to park)**, **including the top-level domain (TLD)**:
   * If you're using HelioHost's domains, specify either **helioho.st** or **heliohost.us**
   * If you've purchased a custom domain, specify the TLD (such as **.com**, **.net**, etc.)
3. The **destination for the alias (the existing domain on your account you want to duplicate)**

The alias will be configured to reflect your `httpdocs` directory. If you want it to reflect a different directory, you will need to request an [Addon Domain](#Addon-Domains) instead.

### Aliases Attached to Custom Domains

### Nameservers

You will need to point the alias on your custom domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

### DNS Records 

If you prefer to add A records (IPv4) or AAAA records (IPv6) to the alias on your custom domain registrar's dashboard instead of nameservers, look up the IP addresses for your server by using the steps below:

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**

### What do I do now?

Whether you are using one of HelioHost's domains or a custom domain, you will need to wait **up to 2 hours** for your alias to become fully active. If after an entire 2 hours, you still see a message saying `HelioHost Account Queued`, please [clear your web browser cache](../misc/clear-your-cache.md).

### Checking DNS for Aliases Attached to Custom Domains

Full DNS propagation can take up to 24 - 48 hours globally in some cases. To check that your DNS is properly configured, go to [https://dnschecker.org](https://dnschecker.org/). Select the type of record you want to check (NS record, A record, or AAAA record), and type in your alias.