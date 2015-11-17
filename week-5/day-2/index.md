# Tuesday November 17


## Daily JS

### Click Button

From yesterday's assignment, create a click button that increments the text of how many "Likes" for every time it is clicked.

```js
var num = 0;

$('button').on('click', function() {
  num++;

  $(this).html(`${num} Likes`);

  if (num === 1) {
    $(this).html(`${num} Like`);
  }
});
```

## Topics

* AJAX
* Promises
* HTTP Verbs

## Code

https://github.com/tiy-lr-fee-2015-fall/lesson-05-02

## Assignment

https://github.com/TIY-LR-FEE-2015-Fall/assignments/tree/master/16-image-board
