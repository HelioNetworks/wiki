# Cron Jobs

In Plesk, cron jobs are called `Scheduled Tasks`. 

To access the cronjob section, navigate to:

**Login > Plesk > Websites & Domains > [ domain ] > Scheduled Tasks > `Add Task`**

![Scheduled Tasks](../../.gitbook/assets/plesk-scheduled-tasks.png)

{% hint style="info" %}
Scheduled tasks run in a chroot environment with limited access to binaries and executables.  

This means you cannot directly access certain programs or scripts outside of your home directory.
{% endhint %}

To work around the chroot, you can create a Flask or Python CGI endpoint like `domain.helioho.st/update` and then use the "Fetch a URL" option inside Scheduled Tasks to access it via `https`.

![Schedule a Task](../../.gitbook/assets/plesk-schedule-a-task.png)