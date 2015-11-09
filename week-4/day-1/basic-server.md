# Basic Node Web Server

Since we have a basic idea of what is a server, let's now look at how we can make one using Node.js.
At it's core, a server needs to know what to listen for and how to respond to requests.
So for this basic server, let's make something that responds by saying "Hello Node.js".

## Requiring HTTP

There is a lot that goes on under the hood to make HTTP requests work and properly send data.
Node.js provides all of this base functionality out of the box in an `http` module that we can use.
To get started let's pull in the `http` module using the `require` function in Node:

```js
var http = require(`http`);
```

Now we can use the `http` variable to work with incoming requests to our web server.

> **NOTE** Unlike some of the other Node modules we've used so far, `http` is included in the core of Node.js so we do not have to use NPM to install anything.
> But, as we'll see, for more complex HTTP servers we will likely want to pull in other dependencies.

## Creating a Server

To create a new server, we need to call the `createServer` function on `http` and send in a callback.

```js
var server = http.createServer(app);
```

At it's core, a Node web server is just a callback is called every time someone makes a request to our site.
This callback has `request` and `respsone` objects as it's two arguments which allow us to work with incoming and outgoing information.

So, let's make the `app` callback that we passed in to `createServer` but don't have yet:

```js
var app = (req, res) => {
  res.end(`Hello Node.js`);
};
```

The `end` method on the response object allows us to send a response back to the client with a set of text content.

## Starting the Server

The `createServer` only sets up what a server would look like, we still need to actually start the server.
To do this, we'll call the `listen` method on any server object and pass in a port number to listen on.

```js
server.listen(3000);
```

This tells the server that we've set up to start listening for incoming web traffic.

## Server vs Client

One of the big things to remember when working with writing server side code is that the browser has no connection to what the server has to do to make a request work.
So if we run `console.log` in our server code, this will log to the terminal running our server NOT the console of the browser.

## Did the Server Start?

For now, we can see that our server is running by going to `http://localhost:3000`, but there's no way from the server to know that things starting without an error.
To know when things start up, the `listen` method on server objects can take a callback that will be run when the server starts up.
So, let's log that our server has started:

```js
server.listen(3000, () => {
  console.log(`Started Server`);
});
```

## Counting Visitors

Since our Node.js app is a long running task, we can use variables in memory to carry information over between different requests.
Let's make our app count how many visitors have come to our app.
To start let's make a `visitor` variable in our global scope.

```js
var visitor;
```

Now we'll want to make sure that this variable is reset any time our server restarts:

```js
server.listen(3000, () => {
  console.log(`Started Server`);

  visitor = 0;
});
```

Then in our `app` callback we can respond with a little bit of HTML that shows the user their visitor number:

```js
var app = (req, res) => {
  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
};
```

But, if we look at this in our browser, it will always show "You are visitor 0".
This is because we've never changed our `visitor` value.
So, before sending the request, let's increment `visitor`:

```js
var app = (req, res) => {
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
};
```

## Request Object

If we look at this in the browser, we'll see that the visitor count goes up by two each time.
To figure out what's going on, let's log each time a visitor hits our server:

```js
var app = (req, res) => {
  console.log('visit');
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
};
```

Now, we are having two visits each time we reload the browser?
To figure out what's going on, we'll need to do some more investigation.
In our `app` callback, we have a request object that has all of the information about the incoming request.
This includes the `url` that is being requested, so let's log that and see if we can figure out why we are seeing two visits:

```js
var app = (req, res) => {
  console.log(`visit: ${req.url}`);
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
};
```

Now we can see that each request in the browser actually makes a request to `/` AND `/favicon.ico`.
So we have to be aware that the callback for our server is called for ANY incoming web traffic on our port.
We could start writing a bunch of `if` statements within this callback to check different info from the request and send different responses, but this could ugly REALLY quickly...
