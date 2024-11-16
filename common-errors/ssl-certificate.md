# SSL Certificate Problems

## Let's Encrypt Settings

Navigate to the Let's Encrypt settings using the steps below:

**Login > Plesk > Websites & Domains > [ domain ] > Dashboard tab > Security section> SSL/TLS Certificates button > Let's Encrypt settings**

## Troubleshooting 

If you have issues with the Let's Encrypt SSL certificate on your domain or subdomain, here are some things to check:

## Check if the Certificate is Expired or Invalid 

If the certificate is expired or invalid:

* Reissue the certificate
* Wait a full 2 hours
* [Clear your cache](misc/clear-your-cache.md) to ensure the changes are applied correctly

## If the Certificate is NOT Expired

If the certificate is not expired:

* Unassign the certificate from the domain
* Reassign the certificate to the domain
* Wait a full 2 hours
* [Clear your cache](misc/clear-your-cache.md) to ensure the changes are applied correctly

## Further Support

If after following the above steps, waiting a full 2 hours, and [clearing your cache](misc/clear-your-cache.md), the problem is not fixed, please post a topic in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add). Make sure you provide your **username**, **domain name**, and any applicable **error message(s)** received.