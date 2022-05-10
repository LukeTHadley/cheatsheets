# Node.js with React starter guide

This guide will show you through creating two different `node.js` services, one acting as the client/frountend, and another acting as the server/backend.

### Getting started with the server/api

##### Creating general project structure

First thing to do is to set up the general project structure for the server and initialise the project:

```shell
$ mkdir node-react-project
$ mkdir node-react-project/server
$ cd node-react-project/server
$ npm init -y
```

##### Initialise the node.js project

The `npm init` command will create a new `package.json` file which will allow us to keep track of all of the scripts and manage any dependencys. 
The `-y` flag simply will generate an empty project without going through the interactive process, saying `yes` to all questions.

The code for the `server` will be held in the `/server/` directory.

Create another folder for the source code for the server:

```shell
$ mkdir api
```

##### Create the index.js file

Create a new file in the `/api/` directory called `index.js` with the following code:

```js
// src/index.js

const express = require("express");

const PORT = process.env.PORT || 3001;

const app = express();

app.listen(PORT, () => {
  console.log(`Server listening on ${PORT}`);
});
```

##### General project strucutre so far

So far the project structure should look like this:

```shell
$ tree node-react-project 
node-react-project
└── server
    ├── package.json
    └── src
        └── index.js
```

##### Installing Express.js

[Express.js](https://expressjs.com/) is a backend framework for Node.js designed for building web applications and API's.

In the `/server/` directory, run the command:

```shell
npm i express
```

This will download some dependencys for `Express` in a new `node_modules` directory as well as a `package-lock.json` file to manage thoes dependencys.

##### Referencing our index.js file in `package.json`

In order for our node application to know about our `index.js` file we must reference it in the `package.json` file as follows:

```js
// server/package.json
...
"scripts": {
  "start": "node src/index.js"
},
...
```

##### Running the service

At this point we can run the node service for the first time and see the output

```shell
$ npm start

> server@1.0.0 start
> node src/index.js

Server listening on 3001
```

If you navigate to `localhost:3001` in your browser you should see `Cannot GET /`, which means everything has worked so far.

### Creating an API Endpoint

We want to user our Node and Express server as an API so that it can give data to our React app.

We will simply create a new endpoint for the route `/api` that will repsond with the JSON data with a message saying "Hello from server!".

Add the following code into `src/index.js` just above the `app.listen(PORT...` line.

```js
app.get("/api", (req, res) => {
    res.json({ message: "Hello from server!" });
});
```

Then restart the service using `npm start` and navigate to `localhost:3001/api` where you should then see the JSON message.

### Creating the React frountend

Navigate to the route `node-react-app` directory and run the command `npx create-react-app client` which will create a new React app with all of its dependencys.

Sometimes when doing this it might come up with the following saying that there are vulnerabilities. Not too sure how to fix this without breaking the entire app.

```shell
12 vulnerabilities (5 moderate, 7 high)

To address all issues (including breaking changes), run:
  npm audit fix --force
```

For some reason this will initialise this new `/client/` directory as a new git root, but if you are generating this in one project this is useless so just remove `.git` and `.gitignore`.

Add the following to the `client/package.json` file to reference the API as a proxy.

```js
"proxy": "http://localhost:3001",
```

### Creating multiple pages using `react-router`

























### References/Resources

https://www.freecodecamp.org/news/how-to-create-a-react-app-with-a-node-backend-the-complete-guide/

https://nodejs.dev/learn

https://reactjs.org/

https://stackoverflow.com/questions/70374005/invalid-options-object-dev-server-has-been-initialized-using-an-options-object

https://nextjs.org/

https://nextjs.org/learn/foundations/about-nextjs?utm_source=next-site&utm_medium=homepage-cta&utm_campaign=next-website

https://nextjs.org/learn/foundations/from-javascript-to-react