# Next.js

## About Next.js

[https://nextjs.org/](https://nextjs.org/) is a popular full stack framework for node.js, it utilizes react for frontend and is packed with awesome features like serverside rendering. It also includes API routes and much more.

## Setup

Go into your project root (if you don't have a project, learn how to create one here [https://nextjs.org/learn/basics/create-nextjs-app](https://nextjs.org/learn/basics/create-nextjs-app))

Create a new file start.js and put this inside:

```javascript
const path = require('path');
const nextPath = path.join(__dirname, 'node_modules', '.bin', 'next');

process.argv.length = 1;
process.argv.push(nextPath, 'start');

require(nextPath);
```

## Server setup

Upload all your files to your Tommy server. Then go to the Node.js section and set the following.

* Node.js Version: At least 14.21.0 tho i highly recommend using the latest one 17.9.1
* Application Root: / (folder where you uploaded your next project, i recommend / )
* Application Startup File: start.js (file we created earlier)
* Custom environment variables: PORT = 8888
* Optionally: Custom environment variables: NODE\_ENV = production

## Starting the server

Once all of the above steps are done, you can press the Enable Node.js button.

Then you need to press the NPM install button.

And then Run script, Script name: build

After that finished you just need to wait for the server to update your account and start using Node.js, this may take a while.
