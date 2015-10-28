# Thursday October 29


## Daily JS

### Logic and "Truthiness"

```js
var x = 10;

var y = function(wat) {
  console.log(wat);

  return wat === 10;
};

var z = 'no';

var a = (foo) => {
  if (foo) {
    console.log(`a works with ${foo.toString()}`);
  }
}

if (x) {
  console.log(`x is truthy?`);
}

if (y) {
  console.log(`y is truthy?`);
}

if (z) {
  console.log(`z is truthy?`);
}

if (y(`10`)) {
  console.log(`y('10') is truthy?`);
}

if (a()) {
  console.log(`a() is truthy?`);
}

if (a(null)) {
  console.log(`a(null) is truthy?`);
}

if (a(10)) {
  console.log(`a(10) is truthy?`);
}


/* Results */

```

## Topics

- [SASS Mixins](mixins.html)
- [SASS Extends](extends.html)
- [Bourbon](bourbon.html)
- [Neat](neat.html)
- [Deploying To Github Pages With Broccoli](gh-page.html)

## Resources

- [Bourbon Docs](http://bourbon.io/)
- [Neat Docs](http://neat.bourbon.io/)

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/07-blog
