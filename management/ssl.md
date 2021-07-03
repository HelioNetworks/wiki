# Using SSL

## SNI

Our server's support of [Server Name Indication \(SNI\)](https://en.wikipedia.org/wiki/Server_Name_Indication) means SSL certificates can be installed without the need for a dedicated IP address.

## Getting an SSL certificate

Our server includes AutoSSL, a feature provided by cPanel allowing the automatic generation of SSL certificates. Therefore, you do not need to do any particular action in order to get a free SSL certificate, which will get automatically installed. However, the process usually takes some time, depending on the current rates of certificate creation. Our AutoSSL-generated certificates are directly from cPanel, Inc \(Sectigo\).

{% hint style="info" %}
Since Johnny does not support AutoSSL, you can follow [this tutorial](johnny-ssl.md) to get SSL working.
{% endhint %}

## Dedicated IP

We no longer require a dedicated IP address for SSL on any of our servers. However, some browsers or operating systems that do not support SNI will show errors. The most common browser/OS that doesn't support SNI is Internet Explorer on Windows XP. A dedicated IP means that your website is separate from all the other HelioHost sites. This offers a few advantages such as not being blocked from sending email if our server gets flagged for spam.

Our provider charges us $20/year for a dedicated IP. We simply pass that cost onto you. You can also buy a dedicated IP for $2 per month.

If you wish to purchase a dedicated IP for $20, please [send your payment to admin@heliohost.org via PayPal](https://www.paypal.me/HelioHost). Once the transaction is complete create a new topic in the [Customer Service forum](http://www.helionet.org/index/forum/45-customer-service/) on HelioNet with your PayPal transaction ID and account information \(username, main domain, and server\), and we will add the dedicated IP to your account.

