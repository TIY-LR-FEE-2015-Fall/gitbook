# Thursday December 10

## Ember Testing Day 3

### In Class app

We will continue working on Pizza Planet

> Create a home page for Pizza Planet, the finest pizza in the galaxy.
> Guests will want to see the available pizzas and awesome arcade games.
> Employees will want to log in to a back of house dashboard and manage both pizzas and arcade games.

### Topics

- Components
  * Integration Tests
    - How does this piece of the app interact with a few pieces?
    - Does not tell a full story
    - Examples:
      * A form gets filled out and captures input
      * A form errors if the fields are not filled in
- Arrange, Act, Assert
  * Arrange: Setup all the data that needs to be tested
    - Unit Tests (Computed Properties): Create instance of model
    - Acceptance Tests: Visit page
    - Integration Tests: Render HBS and setup Listeners
  * Act: Run required interaction with tested code
    - Unit Test (Functions/Helpers): Run function
    - Unit Test (Computed Properties): Change properties
    - Acceptance Tests: `fillIn`, `click`, etc
    - Integration Tests: User interaction
  * Assert: Check expected results
  * Using Hoisting to Organize Component Tests
- Writing Basic Helpers
  * Fill In Form Inputs

### Lab
