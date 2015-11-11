# Monday November 9


## Daily JS

### DOM Manipulation

Write a class/Constructor called Pokemon

A Pokemon should have
- A constructor with `name` and `hp` arguments
- An `attack` method that returns half of the current Pokemon's `hp`

```js
function Pokemon(name, hp) {
  this.name = name;
  this.hp = hp;
}

Pokemon.prototype.attack = function() {
  return this.hp / 2;
}

var charmander = new Pokemon('Charmander', 14);
console.log(charmander.attack()); // 7
```

## Topics

- Attention & Productivity Hacks
- jQuery
- Babel
- Modules

## Code

https://github.com/TIY-LR-FEE-2015-Fall/lesson-04-03

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/14-jquery-ui
