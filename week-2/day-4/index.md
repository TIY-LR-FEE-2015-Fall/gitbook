# Thursday October 29


## Daily JS

### Logic and "Truthiness"

```js
var hi = false;

var x = 20;

var y = function(wat) {
  console.log(wat);

  return wat === 10;
};

var z = 'false';

var a = (foo) => {
  if (foo) {
    console.log(`a works with ${foo.toString()}`);
  }
}

if (x) {
  console.log(`x is truthy?`);
}

if (hi) {
  console.log(`hi is truthy?`);
}

if (noexist) {
  console.log(`noexist is truthy?`);
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
// "x is truthy?"
// REFERENCE ERROR (noexist is not defined)
// "y is truthy?"
// "z is truthy?"
// "10"
// "a works with 10"
```

| Truthy                | Falsey         |
| :-------------        | :------------- |
| true                  | false          |
| all numbers except 0  | 0              |
| all non-empty strings | ''             |
| all objects           | undefined**    |
| all arrays            |                |
| functions*            |                |


\* talking about functions not the actual evaluated values when a function is called
\*\* when undefined doesn't throw a reference error

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
