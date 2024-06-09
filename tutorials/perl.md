# Perl

Perl is one of the most established programming languages on the Internet. With its powerful string processing capabilities and the optional availability of almost every library imaginable, Perl is an excellent choice for somebody looking to allow flexibility and expandability. At HelioHost, we offer Perl configured with more than 100 basic libraries and can add additional modules upon request. If you're a Perl developer looking for free hosting, HelioHost is the place to be.

## Details

| **Server** | Path | Version | Loader |
| :--- | :--- | :--- | :--- |
| [Tommy](../servers/virtual/tommy.md) | /usr/bin/perl | 5.16.3 | CGI |
| [Johnny](../servers/virtual/johnny.md) | /usr/bin/perl | 5.16.3 | CGI |

### Other Perl versions

{% hint style="info" %} 
If you need a different version of Perl, you'll need to get a [VPS](https://heliohost.org/vps/).
{% endhint %}

## Enabled

### Extensive set of default libraries

HelioHost offers more than 100 Perl libraries by default on all free hosting accounts.

### Requesting additional Perl libraries

To request additional libraries, please raise a request in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, your **server**, and **the libraries you need** including any relevant **version numbers** for them.

## Disabled

### Root-level Access

As a security restriction, we force each Perl script to run as its HelioHost user through suEXEC. This prevents any actions that require root-level access. This shouldn't be a problem for legitimate uses.

## Getting Started

Perl scripts are easy to configure and run. To test it out with a simple example, follow the steps below:

### 1. Navigate to your main domain

If you were transferred from the old cPanel, your main domain will be parked on the `public_html` directory.  

If you created a new account on Plesk, your directory will be `httpdocs`.

### 2. Create a `perl.pl` file inside the `cgi-bin` directory with these contents:

```text
#!/usr/bin/perl

print "Content-type: text/html\r\n\r\n";
print "Perl as CGI is working...";
```

### 3. Edit file permissions

Edit the `perl.pl` file's CHMOD permissions to `755` (`rwx r-x r-x`).

### 3. Open file in your browser

Navigate to `domain.heliohost.us/cgi-bin/perl.pl` in your browser. If everything is working you should see `Perl as CGI is working...` displayed in your browser.

### 4. Guidance for editing `perl.pl`

Leave the first line as the shebang (`#!/usr/bin/perl`).
Below the shebang, you may write Perl code. 
Ensure you output a `Content-type` header before anything else.

### 5. Further learning

A good tutorial can be found here: [https://perlmaven.com/installing-perl-and-getting-started](https://perlmaven.com/installing-perl-and-getting-started)