# Addon Domains, Subdomains, and Aliases

Addon domains, subdomains, and aliases are vital services which allows you to host multiple websites on your one account. Each HelioHost account can have up to 10 domains for free, and if you need more than 10 domains they can be added for a donation. However, using these services can be confusing, and some problems can occur in the process. But don't worry - this article will help alleviate any confusion.

## Addon Domains

### What is an Addon Domain?

An addon domain is a domain which reflects the contents of a folder in your Plesk File Manager.

### How can I create an Addon Domain?

To create an addon domain, you will need to submit a request containing **your hosting account username**, and **addon domain you want** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

By default the addon domain will be located in your home folder with a name that matches the domain you requested. For instance, if you requested the domain `mydomain.helioho.st` then the default folder would be `/mydomain.helioho.st/`

You will need to point your new domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

### What do I do now?

You will need to wait approximately 2 hours until your addon domain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear your cache](../misc/clear-your-cache.md).

To check that your nameservers \(NS Records\) are properly configured, go to [https://dnschecker.org/](https://dnschecker.org/) select the NS option and type in your domain.

## Subdomains

### What is a subdomain

A subdomain is like an "attachment" to a current domain that reflects a normal directory. For instance, if you didn't want to host your blog in a subdirectory such as `mydomain.helioho.st/blog/` you could make a subdomain `blog.mydomain.helioho.st` instead. For the speed and reliability of the server we recommend using a subdirectory rather than a subdomain though as having too many domains on a server causes the uptime to drop for everyone. For SEO performance it's best to use a subdirectory as well.

### How can I create a subdomain?

To create a subdomain, you will need to submit a request containing **your hosting account username**, **the subdomain you want added**, and **the domain you want the subdomain to be attached to** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

The subdomain will be be configured to display the files located in the matching directory. Therefore, if your document root was `/subdomain.maindomain.helioho.st/` your new subdomain will serve the files located in that directory.

### What do I do now?

You will need to wait approximately 2 hours until your subdomain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear your cache](../misc/clear-your-cache.md).

## Alias Domains

### What is an Alias?

It is like a pet name of a person. You can call that person with his real name \(main domain\) or with pet name \(alias\). Both name points to _single person_. Likewise , You can use two or more domain names for your single web page.

### How does it differ from Addon Domain?

The difference between addon domains and aliases is simply this:

- With addon domains, you build a completely separate site.
- With an alias, it is already built, you just are giving it another domain for the site it is parked on.

### How Aliases can be helpful

Well, let's say your main domain goes down due to the domain host having problems. If this happens, you can reach your site from your alias. That is very convenient, if you ask me!

### How can I create an Alias?

To create an alias, you will need to submit a request containing **your hosting account username**, **alias (domain you want to park)**, and **destination (the existing domain on your account you want to duplicate)** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

The alias will be automatically be configured to reflect your `httpdocs` directory. If you want it to reflect a different directory, you will need to request an `Addon Domain` instead.

You will need to point your new domain to the following nameservers:

* `ns1.heliohost.org`
* `ns2.heliohost.org`

You can also configure the domain to be redirected to another URL. 

### What do I do now?

You will need to wait approximately 2 hours until your alias becomes active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear your cache](../misc/clear-your-cache.md).

To check that your nameservers \(NS Records\) are properly configured, go to [https://dnschecker.org/](https://dnschecker.org/) select NS, and type in your domain.
