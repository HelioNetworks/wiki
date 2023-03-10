# Node.js

## Preface

Node.js is currently only available on the Tommy server.

## About Node.js

As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications. In the Node.js applications many connections can be handled concurrently. Upon each connection, the callback is fired, but if there is no work to be done, Node.js will sleep.

This is in contrast to today's more common concurrency model, in which OS threads are employed. Thread-based networking is relatively inefficient and very difficult to use. Furthermore, users of Node.js are free from worries of dead-locking the process, since there are no locks. Almost no function in Node.js directly performs I/O, so the process never blocks. Because nothing blocks, scalable systems are very reasonable to develop in Node.js.

## How to setup Node.js

Create a new directory in your `home` folder named `node`. Make sure this node directory is **NOT** in your `public_html` folder.

```text
/home/username/node
```

In that folder create an `app.js` file:

```text
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

In cPanel open the [Application Manager](https://tommy.heliohost.org:2083/frontend/paper_lantern/passenger/index.html).

![](../.gitbook/assets/application_manager.png)

Click `+ Register Application`.

![](../.gitbook/assets/register_application.png)

For name enter `Node`, domain just select your main domain, application URL enter `/node`, path enter `node`, and deployment mode, select `Development` so it looks something like this:

![](../.gitbook/assets/node_form.png)

You don't need to worry about environment variables on this simple example. So next click `Deploy`.

In order for the Node.js application to be deployed it requires an Apache restart so this could take anywhere from a few minutes to a few hours. If it's been more than 2 hours and it still isn't working, please open [a customer service ticket](https://www.helionet.org/index/forum/45-customer-service/) and let us know.

Once the Node.js application has been deployed you should be able to go to `domain.heliohost.org/node/` and see the text `Node.js is working.`.

