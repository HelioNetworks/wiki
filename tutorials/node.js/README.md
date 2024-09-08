# Node.js

{% hint style="warning" %}
If you use Node.js, we strongly recommend that you [monitor your site load here](https://heliohost.org/dashboard/load/).

Node apps often require a lot of server resources, and exceeding the account load limits will cause your user account to be [suspended for high server usage](/accounts/suspension-policy.md#high-server-usage).
{% endhint %}

## Supported Versions
<!-- TODO: Add node versions available on Morty when released -->
| Server | Node.js Version                                     |
|--------|-----------------------------------------------------|
| Johnny | 22.8.0, 21.7.3, 20.17.0, 18.20.4, 16.20.2           |
| Tommy  | 22.8.0, 21.7.3, 20.17.0, 18.20.4, 16.20.2           |

## About Node.js

As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications. In Node.js applications, many connections can be handled concurrently. Upon each connection, the callback is fired, but if there is no work to be done, Node.js will sleep.

This is in contrast to today's more common concurrency model, in which OS threads are employed. Thread-based networking is relatively inefficient and very difficult to use. Furthermore, users of Node.js are free from worries of dead-locking the process, since there are no locks. Almost no function in Node.js directly performs I/O, so the process never blocks. Because nothing blocks, scalable systems are very reasonable to develop in Node.js.

## How to setup Node.js

Your Node.js files will go into your home directory (**NOT** `httpdocs`):

![](../../.gitbook/assets/plesk_file_manager.png)

In your home directory folder, create an `app.js` file with these contents:

```javascript
const http = require('http');
const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/html');
  res.end('Node.js is working.');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

In Plesk, go to: `Website & Domains > [domain]` 

![](../../.gitbook/assets/nodejs-link.png)

Here, you're able to configure settings for your application.

![](../../.gitbook/assets/nodejs-settings.png)

You don't need to worry about environment variables on this simple example. Select `app.js` for your startup file. If you have any NPM packages, Plesk can install them for you.

![](../../.gitbook/assets/nodejs-npm-install.png)

{% hint style="warning" %}
Node.js application deployment can take **up to 2 hours** to go into effect as it requires an Apache restart.

After an entire 2 hours, if your Node app is not working for you, please [clear your web browser cache](../../misc/clear-your-cache.md).
{% endhint %}

Once the Node.js application has been deployed you should be able to go to `domain.heliohost.org` and see the text `Node.js is working.`

![](../../.gitbook/assets/nodejs-working.png)

## Further Support 

If it's been more than 2 hours, and the Node.js application still isn't working, please go back and check all of your steps again. If it's been more than a full 2 hours since your changes and it still isn't working please make a new post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username**, **domain**, and any **error message(s)** encountered.