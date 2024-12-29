# Next.js

{% hint style="warning" %}
If you use Node.js, we strongly recommend that you [monitor your site load here](https://heliohost.org/dashboard/load/).

Node apps often require a lot of server resources, and exceeding the account load limits will cause your user account to be [suspended for high server usage](/accounts/suspension-policy.md#high-server-usage) on our [Johnny](../../servers/virtual/johnny.md) and [Tommy](../../servers/virtual/tommy.md) servers. Accounts on our [Morty](../../servers/virtual/morty.md) server will not be suspended but will be charged for account load overages.
{% endhint %}

## About Next.js

[Next.js](https://nextjs.org/) is a popular full stack framework for Node.js, it utilizes React for frontend and is packed with awesome features like server-side rendering. It also includes API routes and much more.

## Node.js on Plesk Uses Passenger

### What is Passenger?

Passenger is a way of running Node.js, Ruby on Rails (RoR), and other applications that normally require a constantly running background process. Instead of the process always running in the background just waiting for connections, Passenger shuts it down if there are no connections. When someone visits the website, Passenger fires up the Node.js (or Ruby, or whatever language you're using) process. If another person visits the website while the Node.js process is still running, page loads will be very fast. If there are no further page hits for 5 minutes or so, Passenger kills the background process.

### Why Does HelioHost Use Passenger?

It doesn't make sense to leave your car running 24/7 in front of your house just in case you need to drive somewhere so it saves you a second to start the engine. This is a massive waste of gas. Likewise, it doesn't make sense to leave Node.js sites running 24/7 just to save a second of load time in case someone needs to view the page. This is a massive waste of memory. At HelioHost, we want to ensure that the server memory is used efficiently so our servers work efficiently for the hundreds of users on our shared hosting platform.

### Will Passenger Slow My Site Down?

A recent speed test on HelioHost servers showed that our app [only took 177ms to load from a cold start](https://gtmetrix.com/reports/node.krydos1.heliohost.org/esvkM1p0/). That's just under 1/5 of a second, roughly the amount of time it takes to blink.

### How Can I Use Passenger?

By following the steps in this tutorial, Plesk will automatically use Passenger to run your Node.js application.

### Can I Change the Inactivity Timeout?

No, the background process timeout is set to ensure fair resource usage for all our users and cannot be changed. If you need more control over memory management, HelioHost offers a range of [VPS plans](https://heliohost.org/vps/) where you can configure your settings, and a 10% discount when you pay for 6 months upfront.

### Can I Prevent My Site from Sleeping?

Passenger is designed to keep our shared hosting servers running efficiently and help keep your account within the [account load limits](../../accounts/suspension-policy.md#account-load-limits). Deliberately preventing your site from sleeping is likely to get your account suspended for [High Server Usage](../../accounts/suspension-policy.md#high-server-usage) on our [Johnny](../../servers/virtual/johnny.md) and [Tommy](../../servers/virtual/tommy.md) servers, and charged for account load overages on our [Morty](../../servers/virtual/morty.md) server.

### What If My Users Cannot Wait For My Site To Load?

If your application is highly time-sensitive and every millisecond of load time matters, HelioHost offers a range of [VPS plans](https://heliohost.org/vps/) and a 10% discount when you pay for 6 months upfront. With a VPS, you won’t share your server with other users, so you can run any continuous process(es) that you want.

## Setup Next.js

First, delete (or rename) the 'index.html' file that comes by default in the 'httpdocs' folder.

Your Node.js files will go into your home directory (**NOT** `httpdocs`):

![](../../.gitbook/assets/plesk_file_manager.png)

Go into your project root (if you don't have a project, learn how to create one [here](https://nextjs.org/learn/basics/create-nextjs-app))

Create a new file called `start.js` and put this inside:

```javascript
const path = require('path');
const nextPath = path.join(__dirname, 'node_modules', '.bin', 'next');

process.argv.length = 1;
process.argv.push(nextPath, 'start');

require(nextPath);
```

## Server Setup

Upload all your files to your server. Then go to the Node.js section and set the following:

* Node.js Version: we recommend using [the latest available](README.md#supported-versions).
* Application Root: `/` (This is the folder where you uploaded your project, we recommend `/`)
* Application Startup File: `start.js` (The entry point of our app, use the file we created earlier.)
* Custom environment variables: `PORT = 8888`
* Optionally: Custom environment variables: `NODE\_ENV = production`

## Starting the server

Once all of the above steps are done, you can press the `Enable Node.js` button.

Then you need to press the `NPM install` button.

And then `Run script`, Script name: `build`

Finally, you will need to wait **up to 2 hours** for the server to update.

{% hint style="info" %}
Node.js application deployment can take **up to 2 hours** to go into effect as it requires an Apache restart. After an entire 2 hours, if your Node app is not working for you, please [clear your web browser cache](../../misc/clear-your-cache.md).
{% endhint %}

## Further Support 

If it's been more than 2 hours, and the Node.js application still isn't working, please go back and check all of your steps again. If it's been more than a full 2 hours since your changes, and it still isn't working even after you [cleared your web browser cache](../misc/clear-your-cache.md), please make a new post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, **domain**, and any **error message(s)** encountered.