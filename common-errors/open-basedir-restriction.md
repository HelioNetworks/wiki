# Error: open_basedir restriction in effect

## What is the open_basedir restriction?

This is a security measure which prevents you from accessing files in someone else's directory. You can only access things inside your home directory.

If your script tries to access files outside your home directory, you will receive an error similar to:

```Warning: function(): open_basedir restriction in effect. File(/filename.php) is not within the allowed path(s): (/home/username.domain.com/:/tmp/) in /home/username.domain.com/httpdocs/filepath/file.php on line 123```

## How to Fix the Error

### Edit Your Configuration

To resolve the error(s), edit your configuration to only try to access things inside your home directory.

For instance, if your software is trying to write to `/var/php/session` you could change it to `/home/maindomain.helioho.st/session`.

### Unable to Edit Your Configuration

If you're not able to edit your configuration, your options are:
* Switch to another software that allows you to configure filepaths to try to access things only inside your home directory. 
* Switch to a [VPS](https://heliohost.org/vps/) where you would have the whole server to yourself and there wouldn't be anyone else's files for you to access.

## Can the open_basedir restriction be disabled or changed?

No. The open_basedir restriction is a `php.ini` directive which has been enabled for the security and privacy of all our users. It cannot be removed or changed. 

{% hint style="info" %}
The only way to not have the open_basedir restriction apply to your hosting account would be to get a [VPS](https://heliohost.org/vps/)
{% endhint %}