# Tuesday October 27


## Daily JS

### Function Arguments

```js
var x = 2;

var y = function(one) {
  return one;
};

function z(one) {
  return one + x;
}

var a = (x = 9, y = 10) => {
  return x * y;
};

var b = (x, y) => {
  return x(y);
};


console.log(y(12));
console.log(y(x));
console.log(z('Five'));
console.log(a(15, 2));
console.log(a(41));
console.log(b(y, x));

/* Results */
//
//
//
//
//
```

## Topics

- [Broccoli](broccli.html)
- [NPM](npm.html)
- [.gitignore](gitignore.html)
- [Bower](bower.html)

## Lab

- [Deploying To Github Pages With Broccoli](gh-page.html)

## Resources

- [Project Structure Updates](../../resources/project-structure)

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/07-positioning-exercise
