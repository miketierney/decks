---
title: "cf-jquery-1"
theme: /css/material.css
---

<h2>Intro to jQuery: Day 1</h2>

**Code Fellows Front-End Dev Accelerator**  
September 16, 2015 / Mike Tierney

===

# jQuery

---

### jQuery offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.

<cite>Jon Duckett, <em>JavaScript & jQuery</em>, page 294 and 296 (for this and the next few slides)</cite>

===

# What is jQuery?

jQuery is a JavaScript library that you include in your web pages as a file. It lets you find elements using CSS-style selectors and then do something with those elements using jQuery methods.

---

### Select Elements

It is simple to access elements using jQuery's CSS-style selectors than it is using DOM queries. The selectors are also more flexible.

---

### Select Elements (Example)

<br>Get all elements by a class name in JavaScript<br>

```javascript
document.getElementsByClassName("foo");
// -> [element, element, element]

$(".foo");
// -> [$element, $element, $element]
```

---

### Perform Tasks

jQuery's methods let you update the DOM tree, animate elements into and out of view, and loop through a set of elements, all in one line of code.

---

### Perform Tasks (Example)

<br>Loop over all of the elements with a class of `.foo` and hide them<br>

```javascript
$('.foo').fadeOut();
```

<br>Loop over all of the elements and get the data from a `data-*` attribute<br>

```javascript
$(".data-objs").forEach(function (index, node) {
  console.log($(node).data("demo"));
});
```

---

### Handle Events

jQuery includes methods that allow you to attach event listeners to selected elements without having to write any fallback code to support older browsers.

---

### Handle Events (Example)

<br>Wait for a click event<br>

```javascript
$("#myButton").on("click", function () { alert("Click!"); });
```

===

# Installing jQuery

jQuery is a file, so it must be loaded in either the `head` or at the bottom of your `body`

<br><aside>_Hint: Load it at the bottom of the `body`_</aside>

---

# Installing jQuery

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>jQuery</title>
</head>
<body>
  <!-- other html markup goes here -->
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
  <script>window.jQuery || document.write('<script src="js/vendor/jquery-1.11.3.min.js"><\/script>')</script>
</body>
</html>
```

===

# Using jQuery

Wait until the DOM is ready. jQuery has a method for that:

```javascript
$(document).ready(function () { // won't run until the DOMREADY event fires
  doAllTheThings();
});
```

===

# jQuery manipulates the DOM.

---

# What's the DOM?

A tree-like structure that allows technologies like JS and jQuery to easily interact with the presentation in the browser.

The HTML from your web page, as loaded into the Browser, each HTML element and the content within crates what are called 'nodes in the DOM'.

---

# DOM is markup

```html
<!DOCTYPE HTML>
<html>
<head>
    <title>This is a title</title>
</head>
<body>
    <h1>This is a header</h1>
    <p>This is some text</p>
</body>
</html>
```

---

# DOM Outline

```
|- Document
|--- HTML
|----- Head
|------- Title
|--------- "This is a title"
|--- Body
|----- h1
|------- "This is a header"
|----- P
|------- "This is some text"
```

---

### Why use jQuery instead of JavaScript?

<br>In short ... IE.<br><br>

Longer: every browser has implemented the various JavaScript features differently. This was worse a few years back; today it's much better.

---

# But that's not the whole story

---

## jQuery is robust

Chances are, if you want to do it, jQuery has it available as a feature. **Don't reinvent the wheel.**

===

# jQuery basics

jQuery's API is fairly consistent, and easy to work with.

```javascript
jQuery(selector).method(arguments);
/* `arguments` is usually a function */
```

More commonly, you see it like this:

```javascript
$(selector).method(arguments);
```

---

### Anatomy of a jQuery method

```javascript
$("#trigger").on("click", function () {/* do stuff */});
```

* `$` - shorthand reference to `jQuery`
* `("h1")` - selector; must be a `'string'`
* `.on()` - method; these are chainable (`$().fadeOut().fadeIn()`, for example)
* `"click", function () {}` - the arguments for the method. In this case, `on` accepts two arguments - the event to be watched (`"click"`) and what to do when the event happens

---

# [Demo]

===

# Efficient Selectors

```javascript
$("body #specificElement .class-name");
```

---

# DON'T DO THIS.

Sadly, that's not even close to the worst I've seen.

---

# Do this instead

```javascript
$(".class-name", "#specificElement");
```

---

## What is this magic?!

jQuery's selector method accepts **two** arguments.

```javascript
$(targetSelector, context);
```

By default, `context` is the `window`, but you can change it.

===

# Callbacks

Many of jQuery's functions use something called `callbacks` to run the code.

---

The best example of this is jQuery's `click` method:

```javascript
$("someElement").click(function () {
  alert("Hello world");
});
```

---

## How it works

jQuery creates an **event watcher** on the `someElement` node (in this case, the event watcher is waiting for a `click` event).

<br>When the click event happens, jQuery has assigned an **event handler** which is run when the event watcher reports the event as having been fired.

---

**Event watcher**

```javascript
$("someElement").click
```

**Event handler** (the **callback**)

```javascript
function() {
  alert("Hello world");
});
```

===

# Preventing "default"

Sometimes you want to just override an elements default behavior.

---

## Mostly used on links

Always used in callbacks.

---

### What do you think will happen?

```html
<a href="http://google.com" id="clickMe">Don't go, Ellie!</a>
```

```javascript
$("#clickMe").click(function () {
  alert("Don't go, Ellie's sister!");
});
```

---

### [DEMO]

---

## How do we stop this?

By "preventing default" &mdash; essentially, forcing the browser to ignore the default behavior of the element with which we're interacting.

---

## It looks like this

```html
<a href="http://google.com" id="clickMe">Don't go, Ellie!</a>
```

```javascript
$("#clickMe").click(function (evt) { // note the argument
  evt.preventDefault(); // this method stops the URL request
  alert("Don't go, Ellie's sister!");
});
```

===

# Keyboard events

Mouse events are pretty common. `click` is just one of them. Keyboard events on the other hand offer up different kinds of interactions, `.keydown()`, `.keypress()` and `.keyup()`.

---

## Why?

It's not uncommon to need keyboard events to manage user input and other user interactions (`ESC` to close a modal anyone?).  

---

## [DEMO]

===

# Popular Methods

You'll probably use these once or twice...

* `$().each`
* `$().click`
* `$().on`
* `$().hide` and `$().show`
* `$().fadeOut` and `$().fadeIn`
* `$().addClass` and `$().removeClass`
* `$().data`

---

## A quick note about `$().data`

`$().data` is a special method that will read content in a `data-*` attribute on your HTML element. For example:

```html
<span id="someNode" data-test="This is an example data object">I have data!</span>
```

```javascript
console.log($("#someNode").data("test"));
// >> "This is an example data object"
```

---

# One caveat

`$().data` will convert longer properties in to `camelCase`.

```
<span data-test-object></span> => $().data("testObject");
```

Data Attributes are a bit like PUA codes - they're meant to be used however you want, but it's easy to abuse them. Unlike PUA codes, when building a more data-heavy application, there are better ways (which we'll learn about in a few weeks).
