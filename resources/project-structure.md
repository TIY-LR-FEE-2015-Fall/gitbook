# Default Project Structure

Here are the files that should appear in every project from now on:

    /
    |-.stylelintrc
    |-index.html
    |-app.css

## Example `.stylelintrc`

```json
{
  "rules": {
    "at-rule-empty-line-before": [
      2,
      "always",
      {
        "except": [
          "blockless-group"
        ]
      }
    ],
    "at-rule-no-vendor-prefix": 2,
    "block-closing-brace-newline-after": [
      2,
      "always"
    ],
    "block-closing-brace-newline-before": [
      2,
      "always-multi-line"
    ],
    "block-closing-brace-space-before": [
      2,
      "always-single-line"
    ],
    "block-no-empty": 2,
    "block-opening-brace-newline-after": [
      2,
      "always-multi-line"
    ],
    "block-opening-brace-space-after": [
      2,
      "always-single-line"
    ],
    "block-opening-brace-space-before": [
      2,
      "always"
    ],
    "color-hex-case": [
      2,
      "lower"
    ],
    "color-hex-length": [
      2,
      "short"
    ],
    "color-no-invalid-hex": 2,
    "comment-empty-line-before": [
      2,
      "always"
    ],
    "declaration-bang-space-after": [
      2,
      "never"
    ],
    "declaration-bang-space-before": [
      2,
      "always"
    ],
    "declaration-block-semicolon-newline-after": [
      2,
      "always-multi-line"
    ],
    "declaration-block-semicolon-space-after": [
      2,
      "always-single-line"
    ],
    "declaration-block-semicolon-space-before": [
      2,
      "never"
    ],
    "declaration-colon-space-after": [
      2,
      "always"
    ],
    "declaration-colon-space-before": [
      2,
      "never"
    ],
    "function-calc-no-unspaced-operator": 2,
    "function-comma-space-after": [
      2,
      "always"
    ],
    "function-comma-space-before": [
      2,
      "never"
    ],
    "function-parentheses-space-inside": [
      2,
      "never"
    ],
    "function-url-quotes": [
      2,
      "double"
    ],
    "indentation": [
      2,
      2
    ],
    "media-feature-colon-space-after": [
      2,
      "always"
    ],
    "media-feature-colon-space-before": [
      2,
      "never"
    ],
    "media-feature-name-no-vendor-prefix": 2,
    "media-feature-range-operator-space-after": [
      2,
      "always"
    ],
    "media-feature-range-operator-space-before": [
      2,
      "always"
    ],
    "media-query-list-comma-newline-after": [
      2,
      "always-multi-line"
    ],
    "media-query-list-comma-space-after": [
      2,
      "always-single-line"
    ],
    "media-query-list-comma-space-before": [
      2,
      "never"
    ],
    "media-query-parentheses-space-inside": [
      2,
      "never"
    ],
    "nesting-block-opening-brace-newline-before": [
      2,
      "always-multi-line"
    ],
    "nesting-block-opening-brace-space-before": [
      2,
      "always-single-line"
    ],
    "no-eol-whitespace": 2,
    "no-missing-eof-newline": 2,
    "no-multiple-empty-lines": 2,
    "number-leading-zero": [
      2,
      "always"
    ],
    "number-no-trailing-zeros": 2,
    "number-zero-length-no-unit": 2,
    "property-no-vendor-prefix": 2,
    "root-no-standard-properties": 2,
    "rule-no-shorthand-property-overrides": 2,
    "rule-nested-empty-line-before": [
      2,
      "always-multi-line",
      {
        "except": [
          "first-nested"
        ]
      }
    ],
    "rule-non-nested-empty-line-before": [
      2,
      "always-multi-line"
    ],
    "rule-properties-order": [
      2,
      [
        "content",
        "counter-increment",
        "counter-reset",
        "quotes",
        "display",
        "visibility",
        "float",
        "clear",
        "overflow",
        "clip",
        "position",
        "top",
        "right",
        "bottom",
        "left",
        "z-index",
        "transform",
        "flex-direction",
        "flex-wrap",
        "flex-flow",
        "justify-content",
        "align-items",
        "align-content",
        "box-sizing",
        "margin",
        "margin-top",
        "margin-right",
        "margin-bottom",
        "margin-left",
        "padding",
        "padding-top",
        "padding-right",
        "padding-bottom",
        "padding-left",
        "border",
        "border-width",
        "border-color",
        "border-style",
        "border-image",
        "border-image-outset",
        "border-image-repeat",
        "border-image-slice",
        "border-image-source",
        "border-image-width",
        "border-top",
        "border-top-color",
        "border-top-width",
        "border-top-style",
        "border-right",
        "border-right-color",
        "border-right-style",
        "border-right-width",
        "border-bottom",
        "border-bottom-color",
        "border-bottom-style",
        "border-bottom-width",
        "border-left",
        "border-left-color",
        "border-left-style",
        "border-left-width",
        "border-radius",
        "border-bottom-left-radius",
        "border-bottom-right-radius",
        "border-top-left-radius",
        "border-top-right-radius",
        "border-block-end",
        "border-block-end-color",
        "border-block-end-style",
        "border-block-end-width",
        "border-block-start",
        "border-block-start-color",
        "border-block-start-style",
        "border-block-start-width",
        "border-inline-end",
        "border-inline-end-color",
        "border-inline-end-style",
        "border-inline-end-width",
        "border-inline-start",
        "border-inline-start-color",
        "border-inline-start-style",
        "border-inline-start-width",
        "border-collapse",
        "border-spacing",
        "flex",
        "flex-grow",
        "flex-shrink",
        "flex-basis",
        "order",
        "align-self",
        "height",
        "width",
        "max-height",
        "max-width",
        "min-height",
        "min-width",
        "columns",
        "column-count",
        "column-fill",
        "column-gap",
        "column-rule",
        "column-rule-color",
        "column-rule-style",
        "column-rule-width",
        "column-span",
        "column-width",
        "outline",
        "outline-style",
        "outline-color",
        "outline-width",
        "background-color",
        "background",
        "background-image",
        "background-repeat",
        "background-position",
        "background-attachment",
        "background-size",
        "background-clip",
        "cursor",
        "box-shadow",
        "color",
        "font",
        "font-family",
        "font-size",
        "font-weight",
        "font-style",
        "font-variant",
        "line-height",
        "vertical-align",
        "text-align",
        "text-decoration",
        "text-transform",
        "letter-spacing",
        "font-kerning",
        "word-spacing",
        "text-indent",
        "white-space",
        "list-style",
        "list-style-image",
        "list-style-position",
        "list-style-type",
        "transition",
        "transition-delay",
        "transition-duration",
        "transition-property",
        "transition-timing-function",
        "animation",
        "animation-delay",
        "animation-direction",
        "animation-duration",
        "animation-fill-mode",
        "animation-iteration-count",
        "animation-name",
        "animation-play-state",
        "animation-timing-function"
      ]
    ],
    "rule-trailing-semicolon": [
      2,
      "always"
    ],
    "selector-combinator-space-after": [
      2,
      "always"
    ],
    "selector-combinator-space-before": [
      2,
      "always"
    ],
    "selector-list-comma-newline-after": [
      2,
      "always"
    ],
    "selector-list-comma-space-before": [
      2,
      "never"
    ],
    "selector-no-vendor-prefix": 2,
    "selector-pseudo-element-colon-notation": [
      2,
      "double"
    ],
    "selector-root-no-composition": 2,
    "string-quotes": [
      2,
      "double"
    ],
    "value-list-comma-newline-after": [
      2,
      "always-multi-line"
    ],
    "value-list-comma-space-after": [
      2,
      "always-single-line"
    ],
    "value-list-comma-space-before": [
      2,
      "never"
    ],
    "value-no-vendor-prefix": 2
  }
}
```

## Example `index.html`

    <!DOCTYPE html>

    <html lang="en">
    <head>
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1">

      <title>Project Title</title>
      <link rel="stylesheet" href="app.css">
    </head>
    <body>
    </body>
    </html>

## Example `app.css`

    /* apply a natural box layout model to all elements, but allowing components to change */
    html {
      box-sizing: border-box;
    }
    *, *:before, *:after {
      box-sizing: inherit;
    }
