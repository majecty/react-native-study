[![Gitpod Ready-to-Code](https://img.shields.io/badge/Gitpod-Ready--to--Code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/majecty/react-native-study) 

React Native Study
==================

A book for studying JavaScript and React Native.

This project is using [mdbook](https://github.com/rust-lang/mdBook) to generate HTML files from markdown files.
This project is using [now.sh](https://now.sh) to deploy it.

Preview page
------------

You can use the command below to preview rendered HTML while you writing the book:

```sh
mdbook watch --open
```

Deploy
------

First, you must build the markdown files to generate HTML files using the command below:

```sh
mdbook build
```

Use the `now` program to deploy the project.

```sh
now --prod
```

