# Using SSL

## SNI

Our servers support [Server Name Indication (SNI)](https://en.wikipedia.org/wiki/Server_Name_Indication), which means SSL certificates can be installed without the need for a dedicated IP address.

## Getting an SSL certificate

Our [Johnny](/servers/virtual/johnny.md), [Tommy](/servers/virtual/tommy.md), and [Morty](/servers/virtual/morty.md) servers include `SSL It!`, a feature provided by Plesk which allows the automatic generation of SSL certificates. You do not need to take any particular action to get a free SSL certificate, it will be automatically installed. However, the process usually takes some time, depending on the current rates of certificate creation. Our `SSL It!`-generated certificates are from `Let’s Encrypt`.

## SSL Troubleshooting

Please refer to our guidance page for help resolving any [SSL Certificate Problems](../common-errors/ssl-certificate.md).

## Dedicated IP

Although no longer required for SSL, we offer Dedicated IPs if you wish to purchase one.

A dedicated IP means that your website is separate from all the other HelioHost sites. This offers a few advantages such as not being blocked from sending email if our server gets flagged for spam.

Our provider charges us $20/year for a dedicated IP. We simply pass that cost onto you. You can also buy a dedicated IP for $2 per month.

{% hint style="danger" %}  
**Do not send payment** before you have: 
1) Submitted justification for needing a dedicated IPv4 and 
2) Received **approval** from an admin  
{% endhint %}

After **an admin has approved your request**, if you wish to purchase a dedicated IPv4 for $20, please [send your payment to **admin@heliohost.org** via PayPal](https://www.paypal.me/HelioHost).

Once the transaction is complete, create a new topic in the [Customer Service forum](http://helionet.org/index/forum/45-customer-service/) and provide the details below:
1) **PayPal transaction ID**
2) **Confirmation that an admin approved your request**
3) **Account username**
4) **Main domain name**
5) **Server name**  
and we will add the dedicated IP to your account.