# Working With Font Awesome and SASS

## Relative Paths and Font Files

Some CSS and SCSS files like Font Awesome may import font files or other assets.
This can cause a problem since the font path is set to be relative to the existing CSS file.
We have to be aware of this and can test things by opening the Chrome Developer tools and seeing if there are any 404 errors.

Luckily for Font Awesome there is a work around for this error (although not all libraries will have this fix).
Instead of adding `bower_components/font-awesome/css` to our `includesPaths` with Broccoli SASS, we can add `bower_components/font-awesome/scss`.
Now, before we `@import 'font-awesome';` in our SASS file, we can set a `$fa-font-path` variable which let's we change where Font Awesome looks up the font files.

What's even cooler than being able to change this to a local file, we have the ability to point this to a CDN instead:

```scss
$fa-font-path: "//netdna.bootstrapcdn.com/font-awesome/4.3.0/fonts";
```
