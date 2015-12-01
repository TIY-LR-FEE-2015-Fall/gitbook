# Ember for Backbone Devs

Now that we have a decent grasp of the basics of Backbone.js, we can use that to compare and understand some concepts in Ember.js.

## Overall Differences

### Automatic Re-Rendering

One of the first things to be aware of in Ember compared to Backbone is that Ember wires up most of the re-rendering logic for us.
It does this by watching for changes in the underlying objects.
This is similar to the way we can use the `on` and `listenTo` methods in Backbone.js to rerun our render function.

### Templates and Handlebars

While Backbone does not specify a particular templating language to use (or any templating at all): Ember is built around templates written in Handlebars.
This templating gives a lot of strength for us separate the display of our application from the logic behind it.
Ember also uses the templates we write in Handlebars to be incredibly efficient in what to change of the existing DOM.
Compare this to the `render` functions of our Backbone apps (and even the `render` functions for Marionette apps), and we are able to change only what needs changing rather than blowing away the entire world.

### Components Are Composable

Components (which we will cover in more detail later) in Ember allow for flexibility and composability in our application flow and structure.
Components are small pieces of UI that can be put together and reused in multiple places around the application.
Components are at the heart of Ember and allow for more modular code that reduces unwanted side-effects and encapsulates logic.

## Router is Key

In Ember.js the router is the heart of the application.
While to some degree we've tried to wire Backbone's router to do something similar, Ember's router handles everything from asynchronous data flow, to error states, and translates this into what Controllers and Components are loaded and active to the user.

## Convention, Convention, Convention OVER Configuration

One thing we will hear in the Ember community (and other framework communities) is the idea of "Convention Over Configuration".
What this means is that the framework is going to do a lot of the heavy lifting for us.
It can do this because ALOT of applications have similar goals and this can be cooked into the framework.

Here be dragons though...
While "Convention Over Configuration" is great at saving time, preventing common mistakes, and offloading more complex tasks (like deciding what parts of the DOM to update): it can have some side-effects too.
There are some small projects or niche problems that Ember isn't built for, this isn't to say that it can't be solved with Ember, but we may have to do a bit more heavy lifting to fight the configuration compared to a more light-weight solution.
The Ember team continues to work hard to make it so that there are fewer places where this is true and they try to make it easier to change the defaults of things, but be warned.

### Ember CLI

Since Ember is convention driven as a framework and community, the core team also has worked hard to make the development experience as straight-forward as possible.
To do this, they have created a full development environment called Ember-CLI.
This tool does everything from running a development server (similar to `broccoli-lr serve`), running tests, building our app, and even generating boilerplate code for us.

The Ember-CLI community also means that we can quickly and easily pull in third-party code.
For instance while it is fairly trivial to pull in [Pure.css](http://purecss.io/) and update our `ember-cli-build.js` (similar to the `Brocfile.js`): it is much easier to run `ember install ember-cli-pure`.
And for more advanced uses such as pulling in a collection of components or other utilities, the process is just as simple.
This allows the Ember community to come together to solve common problems, reduce reinventing the wheel, and increase the quality of our app: all while saving time!

## Views vs Components

Ember Components are most closely related to Backbone Views.
Components encapsulate a piece of UI such as a form or list of items.
Components, like Backbone Views, allow us to capture user actions like `click` or `submit` events.
But, this is where the similarities start to run out.

Ember components automatically re-render when the underlying data is changed.
This means that there are fewer opportunities for the UI that the user sees to be out of sync from the backing data in Ember since the framework handles this watching for us.

### Component Instantiation

Components in Ember also differ in the way we instantiate them (or rather don't).
In Ember, components are created in our Handlebars templates and attributes are passed in much like HTML attributes.
This means to make a `guard-list` component and send it in a `collection` of guards, it could look a bit like this:

```hbs
<div class="row">
  {{guard-list collection=guards}}
</div>
```

This ability to write components directly into our templates also means that our layout becomes easier to move things around.
Compare this to a similar piece of Backbone code (despite the other differences in functionality):

```js
import GuardList from 'views/guard-list';

var list = new GuardList({collection: guards});
list.render();

$('.row').eq(0).html(list.el);
```

### Component Composability (It's Turtles All the Way Down!)

Since Ember Components are instantiated via templates and all components can have templates, this means that a single component could wrap multiple smaller components.
Compare this to Backbone where we created a list of Item Views within a collection view.
However, the level of flexibility and composability afforded by Ember components really goes unmatched without some REALLY heavy lifting in Backbone.

### Nod to the Future of Web Components

The future of the web is the ability to create native web-components.
This means we could drop in a beatles-list with just a small line of code:

```html
<beatles-list collection='["George", "Paul", "Ringo", "John"]'></beatles-list>
```

This would bring in all of the UI built with Javascript, HTML templates, and CSS will be incapsulated.
This is actually already starting to hit browsers with things like the `date` input which is written using HTML, CSS, and Javascript, but is relatively limited to native elements and the API to create these web components is a bit obtuse for now.
Ember is looking at this future and basing a lot of it's structure around Components to mimic the future of native web components.

## Router vs Router

The basic idea of routers in Backbone and Ember are very similar: decide what data to grab and what to show to the user based on the URL.
But, the ways that both frameworks achieve this can be very different.

Backbone practices a simple map where whatever the URL looks like, the Backbone router will call a method on the current router instance.
This leaves all the view and data wiring up to us.

In comparison, Ember bases everything on the router and the router manages most of our app.
This starts at the concept of the route definition where the route map will build out Route objects, templates, and inject them into the DOM for us.

## Promises, Error, and Loading States

One of the hard things about Backbone is wondering when data is done being retrieved from the server and when we can render Views.
Ember Routes use Promises to manage when a route is ready for prime time vs when it is loading (or even when there is an error).
Based on the progress of that promise at the time, Ember will load templates to show to the user.
Doing the same thing in Backbone would be a huge chore.

### Nested Routes

One of the things that Ember allows for is nested routes.
This means that if we want an admin dashboard always have a special navbar and sidebar, we could use a nested route to take care of this and reduce duplication of code in every admin page in our app.
This kind of nesting isn't available using the default Backbone router, and Backbone has no way of managing the DOM for these nested routes.

## Models & Collections vs Ember Data

Models and Collections are arguably the most opinionated pieces of Backbone.js.
Even though these classes are fairly flexibile and allow for different storage mechanisms, there is still a fair amount of wiring to be done.

* For instance when loading a detail view:

* Do we have the model with `id=3` loaded or do we need to grab that fresh from the server?
* If we don't have it right now, is there an API request that might load it first?
* When it's loaded from two sources, how can I make sure which one is most up to date?
* How do I keep two models with the same `id` straight?

These are the kinds of problems that Ember Data tries to solve.
This means that we don't have to worry about things and we can allow better minds and a heavily used codebase do the heavy lifting (are you seeing a pattern with this?).

That being said, Ember Data is not required to use Ember.
We can build an entire app that only uses jQuery's AJAX functions (or even raw XHR requests).
However, as an app grows: the structure and power of a tool like Ember Data becomes very helpful.
