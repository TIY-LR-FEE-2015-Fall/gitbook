# Default Project Structure

Here are the files that should appear in every project from now on:

    /
    |-.gitignore
    |-index.html
    |-app.css

## Example `.gitignore`

    tmp
    node_modules
    bower_components

# Example `package.json`

The `package.json` file is created by running `npm init` and then following through the instructions.
We can use the defaults for now.

To install packages with npm run `npm install --save-dev package-name` where you would replace `package-name` with the package you want to install.
A few example npm packages we've used are:

* `broccoli`
* `broccoli-merge-trees`

# Example `bower.json`

The `bower.json` file is created by running `bower init` and then following through the instructions.
We can use the defaults for now.

To install packages with Bower run `bower install --save package-name` where you would replace `package-name` with the package you want to install.
A few example Bower packages we've used are:

* `normalize-css`
* `font-awesome`

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
