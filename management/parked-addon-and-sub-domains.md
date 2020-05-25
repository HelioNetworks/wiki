# Parked, Addon and Sub Domains

Parked \(alias\), Addon and Sub Domains are vital services which allows you to get the best out of a domain or multiple domains. They have the power to link together multiple domains as well as customizing the URL of your domains. However, using these services can be confusing, and some problems can occur in the process. But don't worry - this article will help alleviate any confusion.

{% hint style="info" %}
To prevent most problems when adding or configuring parked/addon/sub domains, ensure your server's load is below 7.00.
{% endhint %}

### Parked Domains \(Alias\)

#### What is a Parked Domain?

It is like a pet name of a person. You can call that person with his real name \(main domain\) or with pet name \(parked domain\). Both name points to _single person_. Likewise , You can use two or more domain names for your single web page.

#### How does it differ from Addon Domain

The difference between Parked and Addon Domains is simply this:

* With Addon Domains, you build a completely separate site.
* With Parked Domains, it is already built, you just are giving it another domain for the site it is parked on.

Parked Domains allow you to complete the task quickly and efficiently - there is even the option of redirecting a domain to another website.

#### How Parked Domains can be helpful

Well**,** let's say your main domain goes down due to the domain host having problems. If this happens, you can reach your site from your parked domain. That is very convenient, if you ask me!

#### How can I create a Parked Domain?

After logging into your personal cPanel, click on the `Aliases` button and enter the domain you wish to park into the text box provided. Once you are done, submit the form. After that, navigate to your domain registrar's website and configure your domain with the following nameservers:

```text
ns1.heliohost.org and ns2.heliohost.org
```

The parked domain you have just setup will be automatically be configured to reflect your `public_html` directory. If you want it to reflect a different directory, you will need to configure an `Addon Domain` instead.

You can also configure the domain to be redirected to another URL. Just click on `Manage Redirection` and enter the URL you wish to redirect.

#### What do I do now?

You will need to wait approximately 24 hours until your parked domain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then [please clear you cache](../misc/clear-your-cache.md).

To check that your nameservers \(NS Records\) are properly configured, go to [https://byrondallas.heliohost.org/php/tools/dns\_records.php?domain=&rec=NS](https://byrondallas.heliohost.org/php/tools/dns_records.php?domain=&rec=NS).

### Addon Domains

#### What is an Addon Domain?

An addon domain is a domain which reflects the contents of a folder in your cPanel File Manager.

An example of an addon domain is that `mysite.heliohost.org/addon` is the **SAME** as `addondomain.heliohost.org`.

#### How can I create an Addon Domain?

After logging into your cPanel account, click on the `Addon Domains` and fill in the details and submit the form. After that, navigate to your domain registrar's website and configure your domain with the following nameservers:

```text
ns1.heliohost.org and ns2.heliohost.org
```

The parked domain you have just set up will be be configured to reflect the `Document Root` you specified.

#### What do I do now?

You will need to wait approximately 48 hours until your addon domain will become active. If you still see a message saying `HelioHost Account Queued` after that period, then please [clear you cache](../misc/clear-your-cache.md).

To check that your nameservers \(NS Records\) are properly configured, go to [https://byrondallas.heliohost.org/php/tools/dns\_records.php?domain=&rec=NS](https://byrondallas.heliohost.org/php/tools/dns_records.php?domain=&rec=NS).

### Sub Domains

#### What is a Sub Domain

A sub domain is like an "attachment" to a current domain that reflects a normal directory.

An example of a sub domain is `sub.mysite.heliohost.org` being the **SAME** as `mysite.heliohost.org/sub`.

#### How can I create a Sub Domain?

After logging into your cPanel account, click on `Sub Domains` button and fill in the details and submit the form. The sub domain you have just setup will be be configured to reflect the `Document Root` you specified.

#### What do I do now?

You will need to wait approximately 24 hours until your subdomain become active. If you still see a message saying "HelioHost Account Queued" after that period, then please [clear you cache](../misc/clear-your-cache.md).

