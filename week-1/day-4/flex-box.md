# Flexbox

CSS layouts can be tricky when working with items that need to span across their parent element.

Flexbox is a powerful tool with CSS that allows for interesting layouts and common things to be a lot easier than using positioning, floats, and the traditional box model.

## Opting in to Flexbox

Flexbox works on the concept of flex parents and flex children.

Flex Parent elements are created by `display: flex;`.
Note that element acts similar to the `display: block` in the way that the box model effects the current element.

However when we set an element to `display: flex`, all of its direct children now become "flex items".
This means that for flex items, the traditional box model is changed.

<div style="display: flex; background: red;">
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
</div>

```html
<div style="display: flex; background: red;">
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
</div>
```

## Breaking Down Flexbox Basics

Once a flex parent has been created, the first thing that we see is that all of its children begin to line up as if they were floated (without us having to float all of those items).
This is the first hint at what flexbox is doing.

## The "Flex Axis" and `flex-direction`

The flex items begin to lay themselves out ACROSS a "flex axis" in the parent.
This "flex axis" is an invisible line that goes from the left edge to the right edge of the "flex parent" element.

This axis can be changed with the `flex-direction` property which has four different values:

* `row` (default) - Elements line up from left to right
* `row-reverse` - Elements line up from right to left
* `column` - Elements line up from top to bottom
* `column-reverse` - Elements line up from bottom to top

To continue investigating flexbox we will need to look at a few more properties.

<div style="display: flex; flex-direction: column; background: red;">
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
</div>

```html
<div style="display: flex; flex-direction: column; background: red;">
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; background: white; color: blue;">Child</p>
</div>
```

## Breaking Down the `flex` Property

To see flexbox items do something interesting, let's set our "flex children" to have a property of `flex: 1;`.

Now, we can see that the flex children take up the full width of the flex parent.

<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
</div>

```html
<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
</div>
```

What's actually happening under the hood is actually more complicated than it looks at first glance.
The `flex` property is actually a compound property that is setting things for `flex-grow`, `flex-shrink`, and an optional value for `flex-basis`.

The `flex-grow` property describes how the flex container divies up any extra whitespace after the "flex items" line themselves up.
On the other hand `flex-shrink`, tells the browser what to do if the the flex parent doesn't have enough room for all of the "flex item" children.
Then the `flex-basis` says what point should be used to start making the decision to grow or shrink (think of this as sort of being like `width` if the parent `flex-direction` is set to `row`).

So if we want items to grow but not shrink we could set `flex: 1 0`.

Now what does that `1` mean?
This is the multiplier which decides the priority of how elements grow or shrink.
For instance look a slightly modified example from the one above:

<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 3; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
</div>

```html
<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 3; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
</div>
```

Note how the first item is larger than the items the come later.
This is because the `flex: 3` states that the first element will take up 3px of extra whitespace for every 1px given to the other `flex: 1` elements.

> **NOTE** `flex-grow` and `flex-shrink` multipliers do not give a perfect size multiplier, instead they describe the way that extra whitespace or shrinking should be done.

## Easy Grids with Flexbox

Working with flexbox the use of grids becomes trivial.
Let's look at a "Three Up" example:

<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
</div>

```html
<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child</p>
</div>
```

Ok... So this is a bit of a lie watch what happens to our "Three Up" when there are four child elements:

<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
</div>

```html
<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1; background: blue; color: white;">Child</p>
</div>
```

So if we want to keep this as a "Three up grid", we will need to set the `flex-basis` to `33%` and the `flex-shrink` to `0` so that the items don't shrink:

<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
</div>

```html
<div style="display: flex; background: red;">
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
</div>
```

Still no dice, so we'll need another property to help make this work.

## `flex-wrap`

The `flex-wrap` property is placed on the Flex Container and describes what to do with child Flex Items that overflow out of bounds on the `flex-direction` axis.
So, by changing the `flex-wrap` on our parent div, we can get our "Three Up" to start working again:

<div style="display: flex; flex-wrap: wrap; background: red;">
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
</div>

```html
<div style="display: flex; flex-wrap: wrap; background: red;">
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: white; color: blue;">Child Child Child Child Child Child Child Child Child</p>
  <p style="padding: 1rem; flex: 1 0 33%; background: blue; color: white;">Child</p>
</div>
```
