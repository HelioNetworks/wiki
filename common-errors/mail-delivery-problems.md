# Mail Delivery Problems

HelioHost offers [unlimited email accounts](../features/unlimited-email-accounts.md) to our users. Below is a troubleshooting guide to help resolve issues with email delivery.

## Emails Not Delivered

If you get a mail delivery report that says your email could not be delivered, the report should explain why.

If the report says: `Your email has been blocked because the sender is unauthenticated. [Email provider] requires all senders to authenticate with either SPF or DKIM`, we can help you set up these records.

## Emails Going to Spam Folder

If your email recipients say that your emails are going to their spam folder, setting up SPF, DKIM, and DMARC records will help improve email delivery.

## SPF, DKIM, and DMARC Records 

### Set Up SPF, DKIM, and DMARC Records

To help improve the delivery of your emails, you can request that SPF, DKIM, and DMARC records be added to your account. Please create a new topic in our [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and include your hosting account **username** and **domain name** so we can set this up for you.

### Send a Test Email

After the SPF, DKIM, and DMARC records are set up, we recommend sending a test email to [https://www.mail-tester.com](https://www.mail-tester.com/) to check that everything is set up correctly. Your test email should be a regular email, such as your typical newsletter or a standard message (avoid using just "test" as the email content). If your score is below 10/10, please create a new topic in our [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add) and include **the full report link**, your hosting account **username**, and your **domain name** so we can help you fix any remaining issues.

## Further Support 

If you get a different error in the mail delivery report, or if your emails are not delivered and you don't know why, please make a new post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, **domain name**, and details about the problem, including any **error message(s)** received.