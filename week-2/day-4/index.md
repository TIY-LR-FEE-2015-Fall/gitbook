# Tuesday October 27


## Daily JS

### Objects and an intro to `this`

```js
var x = function(one) {
  return one + 10;
};

var y = function() {
  return this.firstName;
};

var z = {
  firstName: 'John',
  lastName: 'Doe',

  somethingCool: x,

  getFirstName: y,

  fullName: function() {
    return `${this.firstName} ${this.lastName}`;
  },

  setName(first, last) { // setName: function(first, last) {
    this.firstName = first;
    this.lastName = last;
  },
};

console.log(x(12));
console.log(y());
console.log(z.firstName);
console.log(z.somethingCool(8)); // Same a x(8)
console.log(z.getFirstName());
console.log(z.setName('Han', 'Solo'));
console.log(z.fullName());

/* Results */
// 22
// undefined
// "John"
// 18
// "John"
// undefined
// "Han Solo"
```

## Topics

- [SASS Mixins](mixins.html)
- [Bower](bower.html)
- [Bourbon](bourbon.html)
- [Neat](neat.html)
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
