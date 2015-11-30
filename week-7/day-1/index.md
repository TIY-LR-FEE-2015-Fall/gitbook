# Monday November 30


## Daily JS

### Backbone Quiz (20mins)

1. The extend function on Backbone objects creates a new working instance of a View, Model, Collection, etc (true/false). **FALSE** (you have to use the `new` keyword AFTER extending from a base class).
2. What Backbone class is used to read in the URL and start up the application state? **Router**
3. What Backbone class abstracts communication to an AJAX API or other storage mechanism? **Model**
4. What Backbone class represents objects that the user is manipulating (the run in the run timer)? **Model**
5. Do you have to use the router to work with Backbone? **No**
6. What Backbone class captures user input? **View**
7. What is the conventional method name for changing what the user sees in a View based on the underlying data? **`render`**
8. What methods could you use to react to a collection or model changing? **`listenTo` `on`**

## Schedule

* Backbone Questions (20mins)
* Backbone Lifecycle (20-40min)
* Backbone Performance (20mins)
* Backbone Marionette (20mins)
* Refactor Exercise C (20mins)
* Refactor Exercise D (20mins)

## Questions About Backbone

#### How to format data?

> Get the data showing up first then figure out formatting or manipulating after you get things to show up?

#### Reduce Function Review

> The first argument was the last returned value or starting value (the snowball or `carry`), the second argument is the current item in the array that is being iterated over.

#### Script Error

> Require.js will throw an uncaught script error when it cannot find a module.
If this happens check your module names on import statements and check that they match your file names (without `.js` on the end).

## Homework

* https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/17-login-form
* https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/18-run-timer
