---
title: "forms"
date: "2022-05-30 02:23"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- #html
---



[[2022-05-25]]

```html
<form action="example.com/path" method="post">

</form>
```

```html
<form action="example.com/path" method="post">
  <input type="text">
</form>
```

```html
<form action="example.com/path" method="post">
  <label for="firstName">First Name:</label>
  <input type="text" id="firstName">
</form>
```

```html
<label for="first_name">First Name:</label>
<input type="text" id="first_name" placeholder="Bob...">
```

```html
<label for="first_name">First Name:</label>
<input type="text" id="first_name" name="first_name">
```

# Sources

https://www.theodinproject.com/lessons/node-path-intermediate-html-and-css-form-basics