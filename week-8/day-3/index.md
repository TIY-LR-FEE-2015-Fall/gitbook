# Wednesday December 9

## Ember Testing Day 2

### Lab

* Work on Run Timer

#### Videos

* [Outside In TDD](https://vimeo.com/146953048)

### Quick Note

To update to the latest version of Ember and Ember data run:

```sh
bower install ember#^2.2.0 ember-data#^2.2.0 --save -F
ember install ember-data@^2.2.0
```

This will update your `package.json` and `bower.json` files while also installing the latest versions.

### In Class app

Create a home page for Pizza Planet, the finest pizza in the galaxy.
Guests will want to see the available pizzas and awesome arcade games.
Employees will want to log in to a back of house dashboard and manage both pizzas and arcade games.

### Topics

- Our Application
  * Acceptance Tests
    - Describes how a user would work within the app
    - Very high level
    - Does not care how things are accomplished
    - Examples:
      * A user can see a list of 6 pizzas on the home page
        - Use raw template
        - Use a model with an array
      * A user can click on "Login" and sees the login form
- Mocking APIs and Data
  * Ember Mirage
    - Installing: `ember install ember-cli-mirage@v0.2.0-beta.1`
    - Pretender routes
      * Allow us to define a custom server response based on input
      * Examples:
        - A user can login with credentials `ryan@theironyard.com`:`password`
        - A user sees and error message when trying to login with other credentials
    - Mirage "Database"
      * Allows us to build Ember friendly API mocks by just defining data
      * Examples:
        - Replace Pizzas with Ember Data
