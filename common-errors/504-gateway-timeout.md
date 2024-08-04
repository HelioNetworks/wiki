# 504 Gateway Timeout

If a server takes too long to complete a request (such as loading a webpage), it will sometimes display the HTTP 504 Gateway Timeout error. This timeout limit is in place to protect the server from slowing down for all users or even crashing due to long-running processes.

## Apache Restarts

Apache restarts happen every 2 hours on Johnny and Tommy servers. During the restart, your site may display a 504 error to visitors. This typically lasts no longer than a couple of minutes and is resolved once Apache has finished restarting.

If you prefer not to have Apache restart, you can sign up for a VPS Plan, where you can leave Apache or Nginx running for months without a restart.

## Software Installation

If you receive a 504 Gateway Timeout error while trying to install software, the installer might be taking longer than the default server timeout settings allow. In this case, you can request that the server execution time limits be extended temporarily. This would give your software installer more time to finish. After installation, HelioHost admins would need to reduce the execution time limits back to their original settings.

## Request Temporary Extension of Server Execution Time Limits

To request a temporary extension of the server execution time limits to install software, please post a topic in the [Customer Support forum](https://helionet.org/index/forum/45-customer-service/?do=add). Make sure you provide your **username**, **domain name**, the **software** you are trying to install, and any applicable **error message(s)** received.

### References

This page is adapted from [this post](https://helionet.org/index/topic/61478-solved-cannot-install-nextcloud-error-504/) on the HelioNet forum.