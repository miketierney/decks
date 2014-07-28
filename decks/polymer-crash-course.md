---
title: "Polymer: A Crash Course"
theme: /css/material.css
---

<img src="/images/polymer-logo.svg" width="600" alt="Polymer">
<h2>A Crash Course</h2>

**Web Components LA**  
July 29, 2014 / Michael Bleigh

<br>**decks.mbleigh.com/polymer-crash-course**

===

# What Are<br>**Web Components**?

---

# **Browser Standards** for App Dev

---

## The **most important** browser technology for developers **since AJAX**

---

# Browser as<br>**App Platform**

---

# Browser as **Operating System**

---

## Why Browser-Native Matters

1. **Performance.** Browsers will be optimized to run Web Components *fast*.
2. **Interoperability.** Native foundation will obviate need for Angular vs. Ember, etc.
3. **Less Overhead.** Lots of needed functionality without loading lib code.
4. **Flow.** Write code that goes with the browser instead of fighting against it.

---

## Four Parts

* **Shadow DOM:** Separate presentation of elements from source structure.
* **Template Tag:** Inert DOM that can be cloned into the document.
* **Custom Elements:** Define your own first-class HTML elements.
* **HTML Imports:** Like `<script src>` but for HTML.

===

# What is **Polymer**?
### **www.polymer-project.org**

---

# **Polyfills** for Web Components

---

# **Sugar** for Defining Elements

---

# Core Elements<br>**Paper Elements**

===

# Using Polymer

---

## Barebones App

```bash
$ mkdir my-project
$ cd my-project
$ bower init
$ bower install --save Polymer/polymer

$ touch index.html

$ mkdir components
$ touch components/hello-world.html
```

---

```html
<!-- index.html -->
<!doctype html>
<html>
  <head>
    <!-- Import the Web Components polyfills -->
    <script src="bower_components/platform/platform.js"></script>
    <link rel="import" href="components/hello-world.html">
  </head>
  <body>
    <hello-world>Hello World!</hello-world>
  </body>
</html>
```

---

```html
<!-- components/hello-world.html -->
<link rel="../bower_components/polymer/polymer.html">

<polymer-element name="hello-world" noscript>
  <template>
    <style>
      :host { 
        color: red; 
        font-size: 36px; 
        font-family: sans-serif;
      }
    </style>
    <content></content>
  </template>
</polymer-element>
```

===

# **Live Coding w/ Ele!**
## It's JSFiddle for Polymer
### https://ele.io/

---

# **github-readme**
## Display GitHub README for a public repo as HTML

<br>[Finished Product](https://ele.io/mbleigh/github-readme)

---

# **chat-message**
## Format messages for a theoretical chat application

<br>[Finished Product](https://ele.io/mbleigh/chat-message)

===

# Questions?
## **@mbleigh / @divshot**