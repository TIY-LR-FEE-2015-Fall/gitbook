# Thursday November 12

## Daily JS

### jQuery Selectors and Events

Using jQuery take the codepen linked below and make the button text say "Clicked"
when the user clicks on the button:

http://codepen.io/rtablada/pen/GpPZgZ?editors=001

```js
var btn = $('button').on('click', function() {
  // This would change the text of all buttons
  // btn.html('<h1>Superman</h1>');

  // This changes the text of only the current button clicked
  $(this).html('<h1>Superman</h1>');
});
```

## Topics

- HTTP
- JSON
- Basic Servers

## Code

https://github.com/TIY-LR-FEE-2015-Fall/lesson-04-04

## Homework

Continue working on the assignment from yesterday.

https://github.com/TIY-LR-FEE-2015-Fall/assignments/14-jquery-ui
