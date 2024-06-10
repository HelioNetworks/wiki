# Manage HelioHost DNS

Currently, users cannot directly manage DNS records (A, CNAME, TXT, and MX) for sites hosted on `helioho.st` and `heliohost.us` domains.

## Google Site Verification

Please refer to our [Google Site Verification tutorial](google-site-verification.md) which explains how users can verify their own domains via [HTML verification](https://support.google.com/webmasters/answer/9008080?hl=en#html_verification) without the need to contact an admin or use external DNS.

## Requesting DNS Record Changes

To add or edit a zone record, please submit a request containing **your account username**, **your domain**, and the **DNS record(s) to add** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

{% hint style="info" %}
All zone record changes take **up to 2 hours** to go into effect as they require an Apache restart. 
{% endhint %}

## Public Availability of DNS Records

Please note that DNS records are publicly accessible by anyone once they are published. This means that any information included in the DNS records, such as IP addresses or other data, will be publicly visible and can be accessed by anyone on the internet. Therefore, there is no need to request to send them privately to an admin.

## User Management of Zone Records

Plesk cannot currently communicate with the DNS system used for HelioHost domains, so the zone editing functionality has been removed from Plesk user options.

Plesk does not offer a product for running DNS on a separate server from the one hosting the websites. Running DNS on the same server would cause memory and performance issues for our users.

While we aim to develop a way for Plesk and the DNS system to communicate, there is no estimated timeframe for when this functionality might be implemented, as there are many higher-priority projects to complete first.

If this functionality is implemented, an update will be announced in the HelioNet [News](https://helionet.org/index/forum/1-news/) section, as well as elsewhere on our site and our social media.