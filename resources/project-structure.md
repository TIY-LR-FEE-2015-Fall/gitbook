# Default Project Structure

Here are the files that should appear in every project from now on:

    /
    |-index.html
    |-app.css

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
