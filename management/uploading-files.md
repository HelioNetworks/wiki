# Uploading Files

## FTP / SFTP

Just one of the ways to upload and modify your website is through [FTP (File Transfer Protocol)](http://en.wikipedia.org/wiki/FTP), which allows you to connect to your site and perform various file operations directly from your computer.

Once connected, you can perform the appropriate actions just as you would with any other file/folder on your computer. Simply drag and drop or copy and paste files to upload them. Right click on a file/folder to perform a variety of actions such as Rename, Delete, and Create Directory.

To connect to your site's FTP server, you will need to use an FTP Client, such as [FileZilla](http://filezilla-project.org/), which is completely free software used by millions across the world. The various settings you will need to connect to the servers are given in the table below.

If you are having problems connecting to the FTP service, then it might be a temporary failure with the service due to high server load. You can retrieve real-time statistics on server load (including FTP service) at [https://status.heliohost.org](https://status.heliohost.org/)

| Parameter | Tommy | Johnny |
| :--- | :--- | :--- |
| Host | `tommy2.heliohost.org` | `johnny.heliohost.org` |
| Port | 1373 | 1373 |
| Protocol | SFTP - SSH File Transfer Protocol | SFTP - SSH File Transfer Protocol |
| Logon Type | Normal | Normal |
| User | Your Plesk username | Your Plesk username |
| Password | Your Plesk password | Your Plesk password |

## FileZilla

### Step-by-step: Connect to your server with SFTP using FileZilla

1. Click `File → Site Manager`
2. Click `New Site`
3. Name it something like `Tommy SFTP` and press enter
4. Enter settings from the table above
5. Click `Connect`
6. Approve the remote server key, and check the box to not ask you about this server again.

{% hint style="info" %}
You can manage your files with SFTP, or FTPS (on Port 21).  
We recommend not using FTP because it is insecure, but it's available too.
{% endhint %}

## Plesk File Manager

The Plesk online file manager is a great built-in facility available to all users as part of HelioHost. It has all the features you could need to manage the files for your website, even the invisible and hidden ones. Follow the navigation steps below to access the Plesk file manager: 

#### Login > Plesk > Websites & Domains > [ domain ] > Files

{% hint style="warning" %}
Do not bookmark your Plesk File Manager, as your visits are not recorded and you will be [suspended for inactivity](https://wiki.helionet.org/accounts/suspension-policy#inactivity-policy) after 30 days.
{% endhint %}

## Net2FTP

Yet another online file manager is net2FTP. Net2FTP can be accessed directly from [its website](http://net2ftp.com/). Alternatively, you can [download a copy](http://net2ftp.com/index.php?state=homepage&state2=3) and run it from your own website.

## WebDAV

WebDAV / Web Disk / File Sharing has been [deprecated in Plesk](https://docs.plesk.com/release-notes/obsidian/deprecation-plan/), however SFTP is a much better choice anyway.
