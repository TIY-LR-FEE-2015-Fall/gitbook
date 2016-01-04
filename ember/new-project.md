# Starting a New Project With Ember

## Create an Ember Project

`ember new <project-name>`

Remember project names cannot start with numbers.

## Upgrade to latest Ember Version

```sh
trash bower_components
npm install --save-dev ember-data
bower install ember#^2.2.0 ember-data#^2.2.0
bower install
```

## Install Common Ember CLI Addons

There are a few Ember CLI addons you may want in your project:

### Ember Simple Form `ember-simple-form`

This helps take in user input and input bindings.
It will send an `onsubmit` action when the user submits within the component.

* [Docs](https://github.com/rtablada/ember-simple-form#ember-simple-form)

### Ember Simple Auth

This package handles user session login and storage.

* [Docs](https://github.com/simplabs/ember-simple-auth#ember-simple-auth)

### Ember Material Lite

This allows for quick prototyping, including inputs, buttons, navbars, and more:

* [Docs](http://mike.works/ember-material-lite/#/badges)

### Ember CLI Mirage

Allows for API and data mocking (most helpful for testing):

* [Docs](http://ember-cli-mirage.com)
