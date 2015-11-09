# Express.js Servers

Express.js is a library of tools that help make working with HTTP servers in Node a lot easier.
It does this by giving a set way of handling types of request based on their URL.
So to start, let's remember what our regular server looked like using just Node's `http` module:

```js
var http = require('http');

var visitor;

var app = (req, res) => {
  console.log(`visit: ${req.url}`);
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
};

var server = http.createServer(app);

server.listen(3000, () => {
  console.log(`Started Server`);

  visitor = 0;
});
```

And now what would this look like with Express?

```js
var express = require('express');
var app = express();

var visitor;

app.use((req, res) => {
  console.log(`visit: ${req.url}`);
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
});

app.listen(3000, () => {
  console.log(`Started Server`);

  visitor = 0;
});
```

So far this doesn't look too different.
The `createServer` seems to be replaced with `express()`.
And then there's this `app.use` call that takes our callback, but what's going on?

## Routing

Right now, we aren't taking advantage of routing which is one of Express's most powerful features.
Once we have an Express app by calling `express()`, we can register different routes to respond to different types of URLs.
Right now, since we are saying `app.use`, we are telling our app to run that callback on EVERY request.
But we can change this:

If we modify our code just a tiny bit, we can get it to only respond to `GET` requests:

```js
app.get((req, res) => {
  console.log(`visit: ${req.url}`);
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
});
```

Right now, this has the same effect as before, but we only are responding to `GET` requests.
Routes are more flexible than just describing what HTTP verb to respond to.
We can also specify the URL that we want to respond to by passing in a string as the first parameter to the `app.get` method:

```js
app.get('/', (req, res) => {
  console.log(`visit: ${req.url}`);
  visitor++;

  res.end(`<h1>Hello Node.js</h1>
    <h2>You are visitor #${visitor}</h2>`);
});
```

Now we'll notice that the visitor count only goes up by one for every reload of our browser.
This is because we are responding ONLY to GET requests to our home page and not to `favicon.ico` anymore.

If we change the URL part of `app.get`, we'll see that our app no longer loads in the browser.
And Express is even nice enough to give us a error message in the browser.

## Other Methods

While we won't cover this quite yet, our app can also respond to other HTTP verbs using different methods:

* `app.all` - any request with a set url pattern
* `app.get` - `GET` requests
* `app.post` - `POST` requests
* `app.delete` - `DELETE` requests
* `app.push` - `PUSH` requests
