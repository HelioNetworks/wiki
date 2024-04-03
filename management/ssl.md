# Using SSL

## SNI

Our servers support [Server Name Indication \(SNI\)](https://en.wikipedia.org/wiki/Server_Name_Indication), which means SSL certificates can be installed without the need for a dedicated IP address.

## Getting an SSL certificate

<!-- TODO: `SSL It!` works on Morty too. Add him into the list of servers below when he gets his own page/goes live. -->

Our [Tommy](/servers/virtual/tommy.md) and [Johnny](/servers/virtual/johnny.md) servers include `SSL It!`, a feature provided by Plesk which allows the automatic generation of SSL certificates. Therefore, you do not need to do any particular action to get a free SSL certificate, which will automatically be installed. However, the process usually takes some time, depending on the current rates of certificate creation. Our `SSL It!`-generated certificates are from `Let’s Encrypt`.

## Dedicated IP

Although no longer required for SSL, we offer Dedicated IPs if you wish to purchase one.

A dedicated IP means that your website is separate from all the other HelioHost sites. This offers a few advantages such as not being blocked from sending email if our server gets flagged for spam.

Our provider charges us $20/year for a dedicated IP. We simply pass that cost onto you. You can also buy a dedicated IP for $2 per month.

If you wish to purchase a dedicated IP for $20, please [send your payment to **admin@heliohost.org** via PayPal](https://www.paypal.me/HelioHost). Once the transaction is complete, create a new topic in the [Customer Service forum](http://helionet.org/index/forum/45-customer-service/) with your **PayPal transaction ID** and **account information** \(username, main domain, and server\), and we will add the dedicated IP to your account.