# Perl

Perl is one of the most established programming languages on the Internet. With its powerful string processing capabilities and the optional availability of almost every library imaginable, Perl is an excellent choice for somebody looking to allow flexibility and expandability. At HelioHost, we offer Perl configured with more than 100 basic libraries, and allow easy installation of all additional CPAN modules through your site's control panel. If you're a Perl developer looking for free hosting, HelioHost is the place to be.

## Details

| **Server** | Path | Version | Loader |
| :--- | :--- | :--- | :--- |
| [Tommy](../servers/virtual/tommy.md) | /usr/bin/perl | 5.16.3 | CGI |
| [Johnny](../servers/virtual/johnny.md) | /usr/bin/perl | 5.16.3 | CGI |

## Enabled

### Extensive set of default libraries

HelioHost offers more than 100 Perl libraries by default on all free hosting accounts.

### Capability to add Perl libraries

To request additional libraries, please raise a request in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, your **server**, and **the libraries you need** including any relevant **version numbers** for them.

## Disabled

### Root-level Access

As a security restriction, we force each Perl script to run as its HelioHost user through suEXEC. This prevents any actions that require root-level access. This shouldn't be a problem for legitimate uses.

## Getting Started

Perl scripts are easy to configure and run. Just create a file in your `cgi-bin` directory under `public_html`, and place the Perl shebang line `#!/usr/bin/perl` on the first line of the file. Below this line you may write Perl code. Make sure you make this file's CHMOD permissions `755`, and output a `Content-type` header before anything else.

A good tutorial can be found here: [http://perlmaven.com/installing-perl-and-getting-started](http://perlmaven.com/installing-perl-and-getting-started)

## Example

Here is an example of a hello world file:

```text
#!/usr/bin/perl

print "Content-type:text/html\r\n\r\n";
print "Hello World!";
```

