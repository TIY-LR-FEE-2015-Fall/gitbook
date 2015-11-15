# Monday November 10


## Daily JS

### DOM Manipulation

The following code is from an app where the speed of a car is accelerated using the `accelerate` function.
But, right now the code is broken, if we call `accelerate()` without passing in any arguments, `speed` will be set to `NaN`.
Try to explain why this is and rewrite the `accelerate` function to fix this error.

```js
var speed = 0;

/* Original */
// function accelerate(amount) {
//   if (amount === undefined) {
//     amount = 0;
//   }
//
//   speed += amount;
// }

function accelerate(amount) {
  if (amount === undefined) {
    amount = 0;
  }

  speed += amount;
}

accelerate(5); // speed is 5
accelerate(); // speed is NaN
```

When no argument is sent to the `accelerate` function then `amount` will be `undefined`.
`undefined` plus a number gives a result of `NaN`.

## Examples

Using `reduce` only to perform a filter then map.
These two statements would return the same result.

```js
characters.filter((item) => {
  return item.age > 12;
}).map((item) => {
  return item.name;
});

characters.reduce((carry, item) => {
  if (item.age > 12) {
    carry.push(item.name);
  }

  return carry;
}, []);
```


## Topics

- [Objects](objects.html)
- [Constructors](constructors.html)
- [Prototypes](prototypes.html)

## Code

https://github.com/TIY-LR-FEE-2015-Fall/lesson-04-01

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/13-constructors
