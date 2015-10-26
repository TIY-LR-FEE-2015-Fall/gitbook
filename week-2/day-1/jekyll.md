# Jekyll

Jekyll is a quick blogging platform that takes Markdown and other files (using plugins) and turns them into pure HTML files.
Unlike other blogging platforms Jekyll is compiled once and then everyone is seeing the same static files, while something like Tumblr or Wordpress looks up the content in a database on every page load.

## Installing RVM

Jekyll uses Ruby to compile our pages to a final state from markdown files and SCSS.
To better facilitate Ruby development, we need to install RVM which allows us to manage the version of Ruby installed on our system AND the global packages (like Jekyll) that we need to use.

To install RVM we need to run:

```sh
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39
\curl -sSL https://get.rvm.io | bash -s stable --ruby
```

You may need to follow some prompts and run `source ~/.zshrc` to get things working properly.

## Installing Jekyll

To install Jekyll, we will use `gem` which is a package manager for Ruby:

```sh
gem install jekyll
```

Now we will have a new `jekyll` command available in our terminal.

## Creating a Jekyll Project

To create a new project with Jekyll run:

```sh
jekyll new myblog
```

This will create a new Jekyll project in a new directory named `myblog`.

## Viewing the Jekyll Site

Usually Jekyll sites are built and then the final static HTML files are viewed on a server.
However, during development and writing, we will often want to see the results of our blog in real time.
For this, the `jekyll` command packs in a server which will rebuild our site and setup a basic local web server for use to view the results.
To run the Jekyll server, within a project run:

```sh
jekyll serve
```

> **NOTE** The Jekyll server does not include any LiveReload functionality so we will still have to refresh our browser to view the results.


## Writing Posts

In Jekyll, posts are stored in the `_posts` directory.
These files will need to be named correctly for Jekyll to properly show our posts.
This naming format is `YYYY-MM-DD-post-title.md`.

Then within our files we will have to have a section of configuration which says what layout should be used, what the title and description of the post are, and what tags should describe the post.
This configuration uses a syntax called `YAML` which means that each line will have a property name then a colon and the value.
The configuration block is kept within a set of three hyphens for example:

```
---
layout: post
title: My New Post
description: This is my first post
tags: [programming]
---
```

Then after this configuration, we can write our post in regular markdown.

> **NOTE** you should not repeat the title or basic description since these will likely be put in by the template.

> **NOTE** To make creating new posts easier you can add this function to the bottom of your `.zshrc` file and then running `jekyll-post` will create a new post and ask you for the `title`, `description`, and `tags`: https://gist.github.com/rtablada/37ed13e62f283c347f37

## Jekyll Layouts

To save time when creating posts, Jekyll allows us to create posts based on a surrounding layout and theme.
These layouts are stored in the `_layouts` directory.

When working with themes, dynamic content can be put in double curly braces (often referred to as moustaches).
Also, `{% %}` blocks allow Ruby code to be evaluated.
This is usually used to include files from the `_includes` directory for things like partials such as the header, footer, etc.

Other than the dynamic variables, the `_layouts` and `_includes` are just regular HTML files and can be modified to personalize your blog.

## SASS with Jekyll

Jekyll will compile SASS files starting with the `css/main.scss` file.
If you want to add extra import statements, it is best to put these files in the `_sass` directory so that they are only compiled when included using an `@import` statement in `main.scss` or another file in `_sass`.
