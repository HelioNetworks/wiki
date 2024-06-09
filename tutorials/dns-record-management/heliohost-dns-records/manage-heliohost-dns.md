# Manage HelioHost DNS

## Requesting DNS Record Changes

Currently, users cannot directly manage DNS records (A, CNAME, TXT, and MX) for sites hosted on `helioho.st` and `heliohost.us` domains.

To add or edit a zone record, please submit a request containing **your account username**, **your domain**, and the **zone record(s) to add** in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add).

{% hint style="info" %}
All zone record changes take **up to 2 hours** to go into effect as they require an Apache restart. 
{% endhint %}

## Public Availability of Zone Records

Please note that records are publicly accessible by anyone once they are published. 

## User Management of Zone Records

Plesk cannot currently communicate with the DNS system used for HelioHost domains, so the zone editing functionality has been removed from Plesk user options.

Plesk does not offer a product for running DNS on a separate server from the one hosting the websites. Running DNS on the same server would cause memory and performance issues for our users.

While we aim to develop a way for Plesk and the DNS system to communicate, there is no estimated timeframe for when this functionality might be implemented, as there are many higher-priority projects to complete first.

If this functionality is implemented, an update will be announced in the HelioNet [News](https://helionet.org/index/forum/1-news/) section, as well as elsewhere on our site and our social media.