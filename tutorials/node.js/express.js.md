# Express.js                        |

## About Express.js
Express.js is a web application framework for Node.js. It provides a set of tools and features to build web applications and APIs quickly and easily. Express.js simplifies common tasks like routing, handling HTTP requests and responses, setting up middleware, and managing sessions. It is lightweight and flexible, allowing developers to structure their applications as they see fit. It is commonly used for building RESTful APIs or server-side applications.

## Setup

{% hint style="info" %}
If you prefer visual guidance, we have a video tutorial available for you to watch **[here](https://www.youtube.com/watch?v=Ak2yI8w-mew&ab_channel=HelioHost)**.  
To follow the written instructions, please continue reading below.
{% endhint %}

Go into your project root (if you don't have a project, you can use this example project [here](https://github.com/HelioNetworks/Node.JS-Example)).

## How to Setup Express.js

Your Node.js files will go into your user directory (NOT `httpdocs`).

![](../../.gitbook/assets/plesk_file_manager.png)

### Note: Delete the content inside `httpdocs`

If you're not using the above example, then create a new file `app.js` and put this inside:

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

## Server Setup

Upload all your files to your server. Then go to the Node.js section and set the following.

* Node.js Version: minimum 14.21.0, though it is recommend to use the latest available, currently 17.9.1.
* Application Root: `/` (This is the folder where you uploaded your project)
* Application Startup File: `app.js` (The entry point of our app, use the file we created earlier)
* Here, you're able to configure settings for your application.

![](../../.gitbook/assets/NodejsSettings.png)

## Starting the Server

Once all of the above steps are done, press the `Enable Node.js` button.

![](../../.gitbook/assets/enableNodeJs.png)

Then you need to press the `NPM install` button.

![](../../.gitbook/assets/NPMInstall.png)

Finally, you will need to wait **up to 2 hours** for the server to update.

{% hint style="info" %}
Node.js application deployment requires an Apache restart.  
Apache is restarted every 2 hours, so please be patient.  
{% endhint %}

If it's been more than 2 hours, and it still isn't working even after you have [cleared your cache](../misc/clear-your-cache.md), then please open a request in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username** and **domain name** so the issue can be investigated.

Once the Node.js application has been deployed, you should be able to go to the domain you selected and see the text `Node.js is working.`