# Monday October 26


## Daily JS

### Functions and Fat Arrow Syntax

```js
var x = function() {
  console.log('hello');
};

function y() {
  console.log('world');
}

var z = () => {
  console.log('yup');
};

var a = () => {
  return 'no';
};


console.log(x);
console.log(x());
console.log(y());
console.log(z());
console.log(a());

/* Results */
// function
// "hello"
// null
// "world"
// null
// "yup"
// null
// "no"
```

## Topics

- [Organizing CSS](organizing.html)
- [BEM Class Names](bem.html)

## Code

https://github.com/TIY-LR-FEE-2015-Fall/lesson-02-01

## Lab

- [Jekyll Blog](jekyll.html)
- [Github Pages](gh-page.html)

## Resources

- [BEM Website](http://getbem.com/)
- [Jekyll Docs](https://jekyllrb.com/)
- [SASS Docs](http://sass-lang.com/guide)
- [How To Write Without Writing](http://blog.codinghorror.com/how-to-write-without-writing/)

## Homework

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/07-blog

> **NOTE** Along with your homework, you should try to apply the concepts of BEM and organization to the homework from last Thursday.
You may optionally change to using SASS for better organization, variables, and what we discussed in class today.
