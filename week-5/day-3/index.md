# Wednesday November 18


## Daily JS

### Dropdown

Given the following HTML make the `.dropdown__content` show up when the parent `.dropdown` is clicked on.

http://codepen.io/rtablada/pen/GpegjX#0

Use jQuery

```html
<ul>
  <li class="dropdown">
    <span class="dropdown__header">Info</span>
    <ul class="dropdown__content">
      <li>About</li>
      <li>Careers</li>
    </ul>
  </li>
  <li class="dropdown">
    <span class="dropdown__header">Product</span>
    <ul class="dropdown__content">
      <li>Features</li>
      <li>Pricing</li>
    </ul>
  </li>
  <li class="dropdown">
    <span class="dropdown__header">Account</span>
    <ul class="dropdown__content">
      <li>Signup</li>
      <li>Login</li>
    </ul>
  </li>
</ul>
```

```js
$('.dropdown').on('click', function() {
  $(this).find('.dropdown__content').slideToggle();
});
```

## Topics

* Backbone Project Scaffold
* Backbone Views
* REST
* Backbone Model
* Backbone Collection

## Code

https://github.com/tiy-lr-fee-2015-fall/lesson-05-03
