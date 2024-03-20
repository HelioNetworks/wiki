# Unlimited Email Accounts

HelioHost offers its users email accounts under their domains. This means that if your domain is `example.com`, you can create email accounts such as `yourname@example.com`. Unlike other free web hosts, HelioHost does not limit the amount of email accounts each domain can host. Since more email accounts do not burden our server, we see no good reason to restrict them.

## Webmail

Any email account you create on HelioHost can be used and managed through a web interface. HelioHost offers multiple webmail software options: 

### RoundCube

RoundCube comes preinstalled within the [Plesk](../management/how-to-access-plesk.md) control panel, and can be accessed by navigating to:

#### Login > Plesk > Mail 

### SquirrelMail and AfterLogic

SquirrelMail and AfterLogic (WebMail Lite v8.6.0 and WebMail Pro v8.6.0) can be user-installed inside Plesk, by navigating to:

#### Login > Plesk > Applications > All Available Applications > Collaboration > Email

![](../.gitbook/assets/plesk-install-email-service.png)

## Supported Protocols

If you would prefer to use an email application (such as Outlook or Thunderbird) or your phone to read and send email, you can do this with your HelioHost email accounts. We offer compatibility with both the POP3 and IMAP protocols for incoming mail, and employ the standard SMTP protocol for outgoing mail. 

For more information on how to set this up, navigate to:

#### Login > Plesk > Email > Email Addresses > [ your email address ] > Click the `i` button > Click `Manual setup` > Enter the IMAP and SMTP info into your mail client

![](../.gitbook/assets/plesk-setup-email-on-device.png)

![](../.gitbook/assets/plesk-setup-email-on-device-2.png)

## Custom Mail

If you wish to use another mail server to handle your domain's email addresses, then HelioHost is the place for you. We allow users to configure custom MX records for their domain, effectively forwarding all email load from HelioHost to a specified mail server.

## SpamAssassin

SpamAssassin is the most popular anti-spam solution for Linux systems and has won awards for its excellent performance. HelioHost offers SpamAssassin with all its accounts, allowing webmasters to prevent spam on their configured email accounts.

