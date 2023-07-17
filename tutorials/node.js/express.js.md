# Express.js                        |

## About Express.js
Express.js is a web application framework for Node.js. It provides a set of tools and features to build web applications and APIs quickly and easily. Express.js simplifies common tasks like routing, handling HTTP requests and responses, setting up middleware, and managing sessions. It is lightweight and flexible, allowing developers to structure their applications as they see fit. It is commonly used for building RESTful APIs or server-side applications.



## Setup

**Note: If you prefer visual guidance, we have a video tutorial available for you to watch. Click [here](https://www.youtube.com/watch?v=Ak2yI8w-mew&ab_channel=HelioHost){:target="_blank"} to access the video. If you want to follow the written instructions, please continue reading below.**

Go into your project root (if you don't have a project, you can use this example project [here](https://github.com/HelioNetworks/Node.JS-Example){:target="_blank"})


## How to setup Express.js

Your Node.js files will go into your user directory (NOT `httpdocs`).

```text
/
```

![](../../.gitbook/assets/FileManger.png)

**Note: delete the content inside `httpdocs`**

if you don't use the example Create a new file `app.js` and put this inside:

```javascript
const http = require('http');
const express = require('express');
const port = 3000;

const app = express();

app.get('/', (req, res) => {
  res.status(200).send('Node.js is working with Express and http.');
});

// Create an HTTP server using the Express app
const server = http.createServer(app);

server.listen(port, () => {
  console.log(`Server running`);
});
```

Create a new file `package.json` and put this inside:

```javascript
{
  "name": "node-test",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node app.js"
  },
  "dependencies": {
    "cookie-parser": "~1.4.4",
    "debug": "~2.6.9",
    "express": "~4.16.1",
    "http-errors": "~1.6.3",
    "morgan": "~1.9.1",
    "pug": "^3.0.2"
  }
}
```

In Plesk, go to "Website & Domains".

![](../../.gitbook/assets/WebsitesAndDomains.png)

Under the domain you'd like to use for Node.js, select `Node.js`.

![](../../.gitbook/assets/NodejsLink.png)

## Server setup
Upload all your files to your Tommy server. Then go to the Node.js section and set the following.

* Node.js Version: At least 14.21.0 tho i highly recommend using the latest one 17.9.1
* Application Root: / (folder where you uploaded your next project, i recommend / )
* Application Startup File: app.js (file we created earlier)
* Here, you're able to configure settings for your application.

![](../../.gitbook/assets/NodejsSettings.png)




## Starting the server

Once all of the above steps are done, you can press the Enable Node.js button.

![](../../.gitbook/assets/enableNodeJs.png)

Then you need to press the NPM install button.

![](../../.gitbook/assets/NPMInstall.png)

After that finished you just need to wait for the server to update your account and start using Node.js, this may take a while.

In order for the Node.js application to be deployed, it requires an Apache restart, so this could take anywhere from a few minutes to a few hours. If it's been more than 2 hours, and it still isn't working, please
open [a customer service ticket](https://www.helionet.org/index/forum/45-customer-service/) and let us know.

Once the Node.js application has been deployed you should be able to go to `domain.helioho.st/` and see the
text `Node.js is working.`.
