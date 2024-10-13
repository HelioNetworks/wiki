# Next.js

## About Next.js

[Next.js](https://nextjs.org/) is a popular full stack framework for node.js, it utilizes React for frontend and is packed with awesome features like server-side rendering. It also includes API routes and much more.

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

No, the background process timeout is set to ensure fair resource usage for all our users and cannot be changed. If you need more control over memory management, HelioHost offers a range of [VPS plans](https://heliohost.org/vps/), where you can configure your settings.

### Can I Prevent My Site from Sleeping?

Passenger is designed to keep our shared hosting servers running efficiently and help keep your account within the [account load limits](../../accounts/suspension-policy.md#account-load-limits). Deliberately preventing your site from sleeping is likely to get your account suspended for [High Server Usage](../../accounts/suspension-policy.md#high-server-usage).

### What If My Users Cannot Wait For My Site To Load?

If your application is highly time-sensitive and every millisecond of load time matters, HelioHost offers a range of [VPS plans](https://heliohost.org/vps/). With a VPS, you won’t share your server with other users, so you can run any continuous process(es) that you want.

## Setup Next.js

Go into your project root (if you don't have a project, learn how to create one [here](https://nextjs.org/learn/basics/create-nextjs-app))

Create a new file called `start.js` and put this inside:

```javascript
const path = require('path');
const nextPath = path.join(__dirname, 'node_modules', '.bin', 'next');

process.argv.length = 1;
process.argv.push(nextPath, 'start');

require(nextPath);
```

## Server setup

Upload all your files to your Tommy server. Then go to the Node.js section and set the following:

* Node.js Version: At least 14.21.0 (though we highly recommend using the latest one: `17.9.1`)
* Application Root: / (Folder where you uploaded your next project, we recommend `/`)
* Application Startup File: `start.js` (the file created earlier)
* Custom environment variables: `PORT = 8888`
* Optionally: Custom environment variables: `NODE\_ENV = production`

## Starting the server

Once all of the above steps are done, you can press the `Enable Node.js` button.

Then you need to press the `NPM install` button.

And then `Run script`, Script name: `build`

After that finishes, you just need to wait for the server to update your account and start using Node.js, this may take a while.
