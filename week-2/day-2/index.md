# Tuesday October 27


## Daily JS

### Function Arguments

When looking at variables or arguments inside of functions, if they are created in the function itself just rename it `functionName_variableName` so that it is clear that these variables are DIFFERENT than variables that exist outside of that function.

```js
var x = 2;

var y = function(foo) {
  return foo;
};

function z(z_foo) {
  return z_foo + x;
}

/* Fat arrow same as
var a = function(x = 9, y = 10) {
  return x * y;
};
 */
var a = (x = 9, y = 10, z = 2) => {
  return x * y;
};

var b = (x, y) => {
  return x(y);
};


console.log(y(12));
console.log(y('hello'));
console.log(foo);
console.log(y(x));
console.log(z('Five'));
console.log(a(15, 2));
console.log(x);
console.log(a());
console.log(a(41));
console.log(b(y, x));

/* Results */
// 12
// hello
// ERROR: foo is undefined
// 2
// "Five2"
// 30
// 2
// 90
// 410
// 2
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
