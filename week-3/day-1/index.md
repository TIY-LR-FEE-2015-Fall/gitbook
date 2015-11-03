# Monday November 2


## Daily JS

### Value vs Reference

```js
// Variable Creation
var x;
// Variable Assignment
x = 10;
var y = x;
y = 12;

console.log(x);
console.log(y);

var z = {firstName: 'Bob'};
var a = z;
a.firstName = 'Tim';

console.log(z.firstName);
console.log(a.firstName);

var b = [15, 25, 30];
var c = b;
c[1] = 100;

console.log(b);
console.log(c);

a = b;

console.log(x);
console.log(y);
console.log(z);
console.log(a);
console.log(b);
console.log(c);

/* Results */
// 10
// 12
// "Tim"
// "Tim"
// [15, 100, 30]
// [15, 100, 30]
// 10
// 12
// {firstName: "Tim"}
// [15, 100, 30]
// [15, 100, 30]
// [15, 100, 30]
```

## Topics

- [Dash & Resources](dash.html)
- [Javascript Syntax Vocab](js-vocab.html)
- [Variable Scope](scope.html)
- [Hoisting and Variables](hoisting.html)
- [Node & Nodemon](node.html)

## Code

- [Basic Example](example.html)

https://github.com/TIY-LR-FEE-2015-Fall/lesson-02-01

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/10-hoisting
