# Parked, Addon and Sub Domains

Parked \(alias\), Addon and Sub Domains are vital services which allows you to get the best out of a domain or multiple domains. They have the power to link together multiple domains as well as customizing the URL of your domains. However, using these services can be confusing, and some problems can occur in the process. But don't worry - this article will help alleviate any confusion.

{% hint style="info" %}
To prevent most problems when adding or configuring parked/addon/sub domains, ensure your server's load is below 7.00.
{% endhint %}

## Parked Domains \(Alias\)

### What is a Parked Domain?

It is like a pet name of a person. You can call that person with his real name \(main domain\) or with pet name \(parked domain\). Both name points to _single person_. Likewise , You can use two or more domain names for your single web page.

### How does it differ from Addon Domain?

The difference between Parked and Addon Domains is simply this:

- With Addon Domains, you build a completely separate site.
- With Parked Domains, it is already built, you just are giving it another domain for the site it is parked on.

Parked Domains allow you to complete the task quickly and efficiently - there is even the option of redirecting a domain to another website.

### How Parked Domains can be helpful

Well, let's say your main domain goes down due to the domain host having problems. If this happens, you can reach your site from your parked domain. That is very convenient, if you ask me!

### How can I create a Parked Domain?

To create a parked domain, you will need to submit a request containing **your hosting account username**, **alias (domain you want to park)**, and **destination (where you want the alias to point to)** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

The parked domain will be automatically be configured to reflect your `public_html` directory. If you want it to reflect a different directory, you will need to request an `Addon Domain` instead.

You will need to point your new domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

You can also configure the domain to be redirected to another URL. 

### What do I do now?

You will need to wait approximately 2 hours until your parked domain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear your cache](../misc/clear-your-cache.md).

To check that your nameservers \(NS Records\) are properly configured, go to [https://byrondallas.heliohost.org/php/tools/dns_records.php?domain=&rec=NS](https://byrondallas.heliohost.org/php/tools/dns_records.php?domain=&rec=NS).

## Addon Domains

### What is an Addon Domain?

An addon domain is a domain which reflects the contents of a folder in your Plesk File Manager.

An example of an addon domain is that `mysite.heliohost.org/addon` is the **SAME** as `addondomain.heliohost.org`.

### How can I create an Addon Domain?

To create an addon domain, you will need to submit a request containing **your hosting account username**, **addon domain you want**, and **document root or destination (the directory or folder you want the addon domain to point to)** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

The parked domain will be configured to reflect the `Document Root` you specified.

You will need to point your new domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

### What do I do now?

You will need to wait approximately 2 hours until your addon domain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear your cache](../misc/clear-your-cache.md).

To check that your nameservers \(NS Records\) are properly configured, go to [https://byrondallas.heliohost.org/php/tools/dns_records.php?domain=&rec=NS](https://byrondallas.heliohost.org/php/tools/dns_records.php?domain=&rec=NS).

## Subdomains

### What is a subdomain

A subdomain is like an "attachment" to a current domain that reflects a normal directory.

A previous use for this was a subdomain like `blog.mysite.heliohost.org` serving the same content as `mysite.heliohost.org/blog`. However, due to search engines now indexing each subdomain as a new and different website, having matching content will negatively affect your SEO score. Therefore, if you wish to use `blog.mysite.heliohost.org` but have people still visiting `mysite.heliohost.org/blog`, you could create a redirect script to ensure they are always forwarded to your new fancy "blog" subdomain.

### How can I create a subdomain?

To create a subdomain, you will need to submit a request containing **your hosting account username**, **the subdomain you want added**, and **the domain you want the subdomain to be attached to** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

The subdomain will be be configured to reflect the document root you specified. Therefore, if your document route was `/public_html/foo` your new subdomain will serve the files located in that directory.

### What do I do now?

You will need to wait approximately 2 hours until your subdomain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear your cache](../misc/clear-your-cache.md).