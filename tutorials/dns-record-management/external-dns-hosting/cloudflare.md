# Cloudflare

## Preface

This tutorial will guide you through the steps necessary to host your DNS on Cloudflare using their free service. You can follow this guide whether your're using one of our hosting servers or one of our [VPS plans](https://heliohost.org/vps/).

## About Cloudflare

Cloudflare is a global CDN (Content Delivery Network) and also a DNS (Domain Name System) hosting service which has both free and paid plans.

## 1. Create a Cloudflare Account

To begin, you will need to sign up for a free Cloudflare account [here](https://dash.cloudflare.com/sign-up?pt=f).

## 2. Setup Your Site on Cloudflare

Go to your [Cloudflare dashboard](https://dash.cloudflare.com/) and at the top of your screen click on `Add site`:

<figure><img src="../../.gitbook/assets/cloudflare_add_site.png" alt=""><figcaption></figcaption></figure>

Enter your domain (without `www`) and click the `Add site` button:

<figure><img src="../../.gitbook/assets/cloudflare_insert_domain.png" alt=""><figcaption></figcaption></figure>

On the bottom of that page, select Cloudflare's free plan and click on the `Continue` button:

<figure><img src="../../.gitbook/assets/cloudflare_plan_selection.png" alt=""><figcaption></figcaption></figure>

Cloudflare will attempt to automatically detect and import your existing DNS records. 

### Manual DNS Record Import

If Cloudflare's automatic fetching fails or does not capture all necessary DNS records, you may need to manually import them. 

{% hint style="info" %}
Follow the steps below to look up the IP addresses to use for your server:  

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**  
{% endhint %}

Select the relevant text block for your server below, and save it as a text file on your computer.

Open the text file in a text editor and: 
* Replace the IP address placeholders (`##.##.###.##` and `####:###:1:1ee::####`) with the IP addresses displayed inside your Plesk account
* Replace the `yourdomain.com` text with your actual domain, without the leading `http://` or `https://`

#### For Johnny:

{% code title="heliohost_johnny_records.txt" %}
```dns-zone-file
;; 
;;  _   _      _ _       _   _           _
;; | | | |    | (_)     | | | |         | |
;; | |_| | ___| |_  ___ | |_| | ___  ___| |_
;; |  _  |/ _ \ | |/ _ \|  _  |/ _ \/ __| __|
;; | | | |  __/ | | (_) | | | | (_) \__ \ |_
;; \_| |_/\___|_|_|\___/\_| |_/\___/|___/\__|
;;
;;
;; Sample DNS records for Johnny server. Please check your IP addresses
;; on your Plesk panel and if needed replace them.
;;

;; A Records
yourdomain.com.	1	IN	A	##.##.###.##

;; AAAA Records
yourdomain.com.	1	IN	AAAA	####:###:1:1ee::####

;; CNAME Records
www.yourdomain.com.	1	IN	CNAME	yourdomain.com.

;; MX Records
yourdomain.com.	1	IN	MX	0 yourdomain.com.

;; TXT Records
yourdomain.com.	1	IN	TXT	"v=spf1 ip4:##.##.###.## ip6:####:###:1:1ee::#### ~all"
_dmarc.yourdomain.com.	1	IN	TXT	"v=DMARC1; p=none"
```
{% endcode %}

#### For Tommy:

{% code title="heliohost_tommy_records.txt" %}
```dns-zone-file
;; 
;;  _   _      _ _       _   _           _
;; | | | |    | (_)     | | | |         | |
;; | |_| | ___| |_  ___ | |_| | ___  ___| |_
;; |  _  |/ _ \ | |/ _ \|  _  |/ _ \/ __| __|
;; | | | |  __/ | | (_) | | | | (_) \__ \ |_
;; \_| |_/\___|_|_|\___/\_| |_/\___/|___/\__|
;;
;;
;; Sample DNS records for Tommy server. Please check your IP addresses
;; on your Plesk panel and if needed replace them.
;;

;; A Records
yourdomain.com.	1	IN	A	##.##.###.##

;; AAAA Records
yourdomain.com.	1	IN	AAAA	####:###:1:1ee::####

;; CNAME Records
www.yourdomain.com.	1	IN	CNAME	yourdomain.com.

;; MX Records
yourdomain.com.	1	IN	MX	0 yourdomain.com.

;; TXT Records
yourdomain.com.	1	IN	TXT	"v=spf1 ip4:##.##.###.## ip6:####:###:1:1ee::#### ~all"
_dmarc.yourdomain.com.	1	IN	TXT	"v=DMARC1; p=none"
```
{% endcode %}

#### For Morty:

{% code title="heliohost_morty_records.txt" %}
```dns-zone-file
;; 
;;  _   _      _ _       _   _           _
;; | | | |    | (_)     | | | |         | |
;; | |_| | ___| |_  ___ | |_| | ___  ___| |_
;; |  _  |/ _ \ | |/ _ \|  _  |/ _ \/ __| __|
;; | | | |  __/ | | (_) | | | | (_) \__ \ |_
;; \_| |_/\___|_|_|\___/\_| |_/\___/|___/\__|
;;
;;
;; Sample DNS records for Morty server. Please check your IP addresses
;; on your Plesk panel and if needed replace them.
;;

;; A Records
yourdomain.com.	1	IN	A	##.##.###.##

;; AAAA Records
yourdomain.com.	1	IN	AAAA	####:###:1:1ee::####

;; CNAME Records
www.yourdomain.com.	1	IN	CNAME	yourdomain.com.

;; MX Records
yourdomain.com.	1	IN	MX	0 yourdomain.com.

;; TXT Records
yourdomain.com.	1	IN	TXT	"v=spf1 ip4:##.##.###.## ip6:####:###:1:1ee::#### ~all"
_dmarc.yourdomain.com.	1	IN	TXT	"v=DMARC1; p=none"
```
{% endcode %}

Save and exit the text file, making sure you replaced all the IP address placeholders and the domain name placeholder with real values. Be careful not to change anything else, as this could break the DNS zone file.

Inside your Cloudflare dashboard, click on `Import DNS Records` and select the text file you saved from the previous step to upload it to Cloudflare.

<figure><img src="../../.gitbook/assets/cloudflare_import_dns_records.png" alt=""><figcaption></figcaption></figure>

### 3. Configure DNS Records

After Cloudflare has imported your DNS records (automatically or manually via the text file), they will display your nameservers. 

Copy and add both nameservers to your domain's nameservers setting inside your domain registrar's dashboard/panel. 

{% hint style="info" %}
If you are unsure how to set nameservers inside your domain registrar's dashboard/panel, please reach out to your domain registrar's customer support.
{% endhint %}

Then, return to your Cloudflare dashboard and click on `Done, check nameservers` in the Cloudflare dashboard.

<figure><img src="../../.gitbook/assets/cloudflare_nameservers.png" alt=""><figcaption></figcaption></figure>

## Manual Cloudflare Configuration

If you want to manually configure your Cloudflare settings, then set the `A` and `AAAA` records for the base domain to the IPs shown in Plesk, and create a CNAME for `www` that’s pointed to your domain.

To view the IP addresses to use for your A and AAAA records, follow the steps below:  

**Login > Plesk > Websites & Domains > [domain name] > and check at the bottom of the page.**  

{% hint style="info" %}
If you need email to work, you will also need additional records: an `MX`, and 2 `TXT` records for `SPF` and `DKIM`.
{% endhint %}