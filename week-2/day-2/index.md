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

- [SASS Mixins](mixins.html)
- [Bower](bower.html)
- [Deploying To Github Pages With Broccoli](gh-page.html)

## Lab

- [Jekyll Blog](jekyll.html)
- [Github Pages](gh-page.html)


## Resources

- [Bourbon Docs](http://bourbon.io/)
- [Neat Docs](http://neat.bourbon.io/)

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/07-blog

## Blog Entry

Tonight I would like for you to blog about what the hardest part of HTML and CSS has been so far.
