# Uploading Files

## FTP/SFTP

Just one of the ways to upload and modify your website is through [FTP \(File Transfer Protocol\)](http://en.wikipedia.org/wiki/FTP), which allows you to connect to your site and perform various file operations directly from your computer.

Once connected, you can perform the appropriate actions just as you would with any other file/folder on your computer. Simply drag and drop or copy and paste files to upload them. Right click on a file/folder to perform a variety of actions such as Rename, Delete, and Create Directory.

To connect to your site's FTP server, you will need to use an FTP Client, such as [FileZilla](http://filezilla-project.org/), which is completely free software used by millions across the world. The various settings you will need to connect to the servers are given in the table below.

If you are having problems connecting to the FTP service, then it might be a temporary failure with the service due to high server load. You can retrieve real-time statistics on server load \(including FTP service\) at [http://heliohost.grd.net.pl/monitor](http://heliohost.grd.net.pl/monitor)

| Parameter | Tommy | Ricky | Johnny |
| :--- | :--- | :--- | :--- |
| Host | `tommy.heliohost.org` | `ricky.heliohost.org` | `johnny.heliohost.org` |
| Port | 1342 | 1312 | 1373 |
| Protocol | SFTP - SSH File Transfer Protocol | SFTP - SSH File Transfer Protocol | SFTP - SSH File Transfer Protocol |
| Logon Type | Normal | Normal | Normal |
| User | Your cPanel username | Your cPanel username | Your cPanel username |
| Password | Your cPanel password | Your cPanel password | Your cPanel password |

### Step-by-step: Connect to your server with SFTP using FileZilla

1. Click `File → Site Manager`
2. Click `New Site`
3. Name it something like `Tommy SFTP` and press enter
4. Enter settings from the table above
5. Click `Connect`
6. Approve the remote server key, and check the box to not ask you about this server again.

## WebDisk

As an alternative to FTP, Web Disk is another useful service for transferring files in an efficient manner. The Web Disk uses the `DAV` protocol, which can be extremely useful in different situations. Although Web Disk is slightly slower and more complicated to setup, it is much more reliable and doesn't require any additional software on most operating systems.

To learn how to use Web Disk, then use the 'Web Disk' section of your personal cPanel. From that section, click on the 'Access Web Disk' button, click on your operating system, and follow the instructions given.

The host is [http://yoursite.heliohost.org:2077](http://yoursite.heliohost.org:2077/) , replacing `yoursite.heliohost.org` with your main domain. cPanel will also allow you to download a script which will automatically setup Web Disk on your computer. If the script fails to work, manually setup Web Disk. If you are still experiencing problems, try using the non-SSL version of Web Disk.

Web Disk acts like any other folder, and can be browsed using your normal file browsing program like Windows Explorer \(for Windows\) and Finder \(for Mac\). On Windows computers, it will be available via 'My Computer'. On Mac computers, your site will be listed under the 'Shared' section of Finder.

## cPanel File Manager

As an online file manager, you can use the built-in File Manager available from your personal cPanel. It has all the features you could need to manage the files in your website, even the invisible and hidden ones. As an online file manager, it is a great built-in facility available to all users as part of HelioHost.

**Warning: Do not bookmark your cPanel File Manager, as your visits are not recorded and you will be suspended for inactivity after 30 days.**

## **PyDio**

 Pydio, formerly known as AjaXplorer, is another online file manager which uses AJAX to provide the best file manager possible. It includes editors in every occasion, multiple users, and more! Pydio is available for download at [https://pydio.com](https://pydio.com/) and you can install by simply dragging and dropping the contents of the ZIP file to your site.

## Net2FTP

 Yet another online file manager is net2FTP. Net2FTP can be accessed directly from [its website](http://net2ftp.com/). Alternatively, you can [download a copy](http://net2ftp.com/index.php?state=homepage&state2=3) and run it from your own website.

