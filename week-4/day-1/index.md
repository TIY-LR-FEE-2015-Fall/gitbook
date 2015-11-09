# Tuesday November 10


## Daily JS

### DOM Manipulation

The following code is from an app where the speed of a car is accelerated using the `accelerate` function.
But, right now the code is broken, if we call `accelerate()` without passing in any arguments, `speed` will be set to `NaN`.
Try to explain why this is and rewrite the `accelerate` function to fix this error.

```js
var speed = 0;

function accelerate(amount) {
  speed += amount;
}
```

## Topics

- [Application State](app-state.html)
- [Objects & Prototypes](prototypes.html)

## Code

https://github.com/TIY-LR-FEE-2015-Fall/lesson-04-02

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/10-hoisting
