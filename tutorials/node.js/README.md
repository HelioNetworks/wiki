# Node.js

## Supported Versions

| Server | Node.js Version                                     |
|--------|-----------------------------------------------------|
| Tommy  | 8.17.0, 10.24.1, 12.22.12, 14.21.3, 16.19.1, 17.9.1 |
| Johnny | 12.22.12, 14.21.3, 16.19.1                          |

## About Node.js

As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications. In the
Node.js applications many connections can be handled concurrently. Upon each connection, the callback is fired, but if
there is no work to be done, Node.js will sleep.

This is in contrast to today's more common concurrency model, in which OS threads are employed. Thread-based networking
is relatively inefficient and very difficult to use. Furthermore, users of Node.js are free from worries of dead-locking
the process, since there are no locks. Almost no function in Node.js directly performs I/O, so the process never blocks.
Because nothing blocks, scalable systems are very reasonable to develop in Node.js.

## How to setup Node.js

Your Node.js files will go into your user directory (NOT `html`).

```text
/home/maindomain/
```

In that folder create an `app.js` file:

```
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

In Plesk, go to "Website & Domains".

![](../../.gitbook/assets/WebsitesAndDomains.png)

Under the domain you'd like to use for Node.js, select `Node.js`.

![](../.gitbook/assets/NodejsLink.png)

Here, you're able to configure settings for your application.

![](../.gitbook/assets/NodejsSettings.png)

You don't need to worry about environment variables on this simple example. Select `app.js` for your startup file. If you have any NPM packages, Plesk can install them for you.

In order for the Node.js application to be deployed, it requires an Apache restart, so this could take anywhere from a few
minutes to a few hours. If it's been more than 2 hours, and it still isn't working, please
open [a customer service ticket](https://www.helionet.org/index/forum/45-customer-service/) and let us know.

Once the Node.js application has been deployed you should be able to go to `domain.heliohost.org/` and see the
text `Node.js is working.`.
