---
title: "Practical Polymer Workflow"
theme: /css/material.css
---

# **Practical Polymer**
## A Web Components Workflow

<br>Web Components LA  
July 29, 2014 / Michael Bleigh

<br>**decks.mbleigh.com/practical-polymer**

===

# Browser Native
## **Tooling Optional**

---

# Well, Kinda

---

## Benefits of Tooling

* Package Management
* Performance Optimization
* Code Generation
* "Standard Way of Doing Things"

===

# The Tools
## **(Node.js Required)**

---

## **Unofficially** Official

---

<img src="/images/bower-logo.png" width="400" alt="Bower">

## Package Management

---

<img src="/images/yeoman-logo.png" alt="Yeoman">

## Code Generation

---

<img src="/images/grunt-logo.png" width="300" alt="Grunt">

## Task Runner

---

<img src="/images/divshot-glyph.png" width="400" alt="Divshot">

## Deploy

===

# Installation

---

# Step One

<pre style="text-align: center; font-size: 0.7em;"><code>npm install -g yo grunt-cli bower generator-polymer</code></pre>

---

# Step Two
## **There is no step two.**

===

# **App Workflow**

---

# Bootstrapping

`mkdir my-app`  
`cd my-app`  
`yo polymer`

---

## App Structure

* **app:** source directory
* **app/bower_components:** packaged elements
* **app/elements:** app-specific elements
* **dist:** build directory
* **bower.json:** dependency list

---

## Handy Commands

* **Development Server:** grunt serve
* **Production Build:** grunt build
* **New Element:** yo polymer:el el-name
* **Package Install:** bower install --save owner/package
* **Deploy:** divshot push

---

# **Live Walkthrough!**

===

# **Package Workflow**

---

# App **vs.** Package

---

# Is it reusable?
## **If so, package it!**

---

# Bootstrapping

`mkdir -p web-components/my-element`  
`cd web-components/my-element`  
`yo polymer:seed`

---

# **Warning!**<br>Bower Gotcha

---

# Package Structure

* **my-element.html:** your element's source
* **my-element.css:** styles for your element
* **index.html:** documentation viewer
* **demo.html:** pretty much what it sounds like

---

# **Live Walkthrough!**

===

# Any Questions?
## **@mbleigh** / **@divshot**