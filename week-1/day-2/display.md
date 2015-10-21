# CSS `display` Property

When working on layout, one of the critical tools is the ability to change HOW elements are rendered and how they decide WHERE to render.

Key to this is the `display` property which dictates how elements interact with other elements in the rendering process.

# `display: block;`

For the ["Div-like elements"](../day-1/elements.html#div-like-elements), and [Parent elements](../day-1/elements.html#parent-elements), the default `display` value is set to `block`.
This means that without other changes (more on this in the [float docs](float.html)), `block` elements will render on their own line within the parent element.
`block` elements will also have `width` and `height` properties that can be set.

# `display: inline-block;`

The only tag that defaults to `inline-block` is the `img` element.
Elements with `display: inline-block;` will act just like `block` elements, however instead of rendering on their own line, `inline-block` elements render inline.

> **NOTE** `inline-block` elements will affect the line height of the current line and will not have let text wrap around it. If you want to have text wrap around an element, use the [`float` property](float.html).

# `display: inline`

The last major value for the `display` property is the `inline` setting.
This works similar to the `inline-block`, however `width` and `height` are only determined by the text content of the element.
The ["Modifier elements"](../day-1/elements.html#modifiers) such as `span` or `strong` tags usually default to being `display: inline` since they are generally used to make subtle modifications to text or font settings and not for layout purposes.

> **NOTE** there is an edgecase where the `width` and `height` of `inline` `img` tags can be set. This is an outlier and `inline-block` should be used to keep consistent styles across all elements with a particular selector.
