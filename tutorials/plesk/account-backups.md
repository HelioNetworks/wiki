# Plesk Account Backups

## Where to Download Your Account Backup

If the HelioHost team made a backup of your hosting account data, you can retrieve it by visiting [https://heliohost.org/backup](https://heliohost.org/backup/) and following the instructions on the page to download the file.

Inside the downloaded backup file, there will be a large file named `backup_user-data_##########.tzst` which contains all your files.  

The file will be in a format called `Z-standard` and will need to be extracted.

## How to Extract Your Account Data from the Backup File

### Linux or Mac

On Linux or Mac you can install the `zstd` package and extract it on the command line. 

### Windows 

On Windows you can use [WinRar](https://www.win-rar.com/) or [7-Zip](https://www.7-zip.org/).

## Access Your Files

* Navigate to the main backup file named `pleskbackup-YourAccountUsername.tar`
* Extract the `.tar` file with the version of 7-Zip you just installed
* The files will be extracted to a folder named `pleskbackup-YourAccountUsername`
* Open the folder and navigate to the `domains` folder
* Open the next folder, named `YourAccountUsername.heliohost.us` or `YourAccountUsername.helioho.st`
* Navigate to the file named `backup_user-data_##########.tzst` 
* Open the file to access your data

### Screenshot Example

![](../../.gitbook/assets/extract-plesk-backup-file.png)

## Making Your Own Manual Account Backup

Follow the navigation steps below to make a backup of your hosting account inside Plesk:  

### Login > Plesk > Websites & Domains > [ domain ] > Backup & Restore

#### Screenshot:

![](../../.gitbook/assets/plesk-make-account-backup.png)

## Scheduling Automated Account Backups

Follow the navigation steps below to set up or modify your scheduled account backup settings inside Plesk:

### Login > Plesk > Websites & Domains > [ domain ] > Backup & Restore > Schedule

![](../../.gitbook/assets/plesk-schedule-account-backup.png)

After clicking the `Schedule` button, adjust the settings as needed.

### Further Support

If after following the above steps, you are unable to download or extract your backup data or make your own account backup, please post a topic in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add). Please make sure you provide your hosting account **username** and details of the problem, including what steps you have tried, and any **error message(s)** encountered.

## References

The original discussion which prompted the creation of this tutorial for extracting Plesk backup files can be found [here](https://helionet.org/index/topic/58777-solved-suspended-account/#comment-260423).