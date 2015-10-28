# Wednesday October 28


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

- [SASS Builds](sass-build.md)
- [SASS Imports](sass-imports.md)
- [SASS Variables & Math](sass-variables.md)
- [SASS Functions](sass-functions.md)

## Lab

- [Font Awesome & SASS](font-awesome-sass.html)

## Resources

- [Project Structure Updates](../../resources/project-structure.html)

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/08-beer-layout
