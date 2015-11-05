# Working With Elements in Javascript

Once we have grabbed an element using `document.querySelector` or grabbing an item from a NodeList after `document.querySelectorAll`, we then can modify the element using different properties and functions on this HTMLElement object.

<p class="superman" style="position: fixed; bottom: 0; right: 0; z-index: 999; background: rgba(0, 0, 0, 0.5); color: white; margin: 0; padding: 1rem;">I'm Superman</p>

For this page, let's assume we have a `superman` element:

```js
var superman = document.querySelector('.superman');
```

<script>
var superman = document.querySelector('.superman');
</script>

> The `superman` element is at the bottom right of this screen and can be modified after each example.

## `innerHTML`

The first property on every HTMLElement object is the `innerHTML` property.
This property allows us to inspect the current contents of an element OR change the text shown.

```js
alert(superman.innerHTML);
```

<button class="alert-innerhtml">Alert `innerHTML`</button>

<script>
document.querySelector('.alert-innerhtml').addEventListener('click', function() {
  alert(superman.innerHTML);
});
</script>

If we assign the `innerHTML` property, we can change the text of the HTMLElement:

```js
alert(superman.innerHTML);
```

<button class="change-innerhtml">Change `innerHTML`</button>

<script>
document.querySelector('.change-innerhtml').addEventListener('click', function() {
  superman.innerHTML = `Changed`;
});
</script>
