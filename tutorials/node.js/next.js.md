# Next.js

## About Next.js

[Next.js](https://nextjs.org/) is a popular full stack framework for node.js, it utilizes React for frontend and is packed with awesome features like server-side rendering. It also includes API routes and much more.

## Setup

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
