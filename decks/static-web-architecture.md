---
title: Static Web Architecture - Not just for hipsters!
theme: /css/static.css
---

# Static Web Architecture
## Not Just for Hipsters!

### Michael Bleigh, Divshot

===

# Follow Along!
* http://decks.mbleigh.com/static-web-architecture
* [@mbleigh](http://twitter.com/mbleigh) on Twitter

===

# Request/Response<br>is Dead.

---

# User Expectations

1. Additional data is loaded without page refresh.
2. Notifications of new data to appear without refresh.
3. Basically, never ever need to refresh.

---

# Users want apps, not sites.

---

# So why do we build request/response apps?

---

# What's the alternative?

===

<h1 class="huge">Static Web Apps</h1>
## Just the files, please.

---

# Typical Web App

1. The browser sends a request to a web server.
2. The server receives the request and information to the web application.
3. The web app connects to data sources based on the request characteristics.
4. The web app uses this data to dynamically generate HTML.
5. The server sends the generated HTML to the browser.

---

# Static Web App

1. The browser sends a request to a static web server.
2. The server sends the corresponding HTML file unmodified to the browser.
3. JavaScript in the page uses the browser to connect to data sources.
4. JavaScript in the page manipulates the HTML to display the fetched data.

---

# Front-End and Back-End are **Completely Separate**

---

# Hybrid Apps
## e.g. Meteor, "Isomorphic", Proxy Cache

===

## I've heard of this, it's a
# Single-Page App
## Why not call it that?

---

<h1 class="huge">Terms Matter</h1>
## "Horseless Carriage"

---

# Two Types of Static Apps

---

<h1 class="huge">Web Clients</h1>
## "Single-Page Applications"

---

# Compiled Content
## Jekyll, Roots, This Slide Deck

===

<h1 class="huge">Why Static Apps?</h1>

---

## "Single-Page Apps are the Fixie Bikes of Web Development"
&mdash;someone on Twitter (paraphrased)

---

# There are **lots** of front-end developers.

---

# Static apps come together fast.

---

# We know how to scale static content.

---

# Static apps are modular from<br> day one.

---

# Separating front and back makes you more flexible.

===

<h1 class="huge">Making Static Apps Work</h1>

---

# Routing: HTML5 History

```js
window.history.pushState({}, "", "/some/new/path");

window.onpopstate = function(event) {
  alert(document.location);
};

```

---

# Cross-Origin Resource Sharing

* Send cross-domain AJAX requests with full security control on the server.
* Using `withCredentials` you can even use cookie-based sessions cross-origin.
* Make your API consumers happy with first-class CORS support (GitHub, AWS)

---

# Offline Apps

* Use HTML5 Cache Manifest to allow offline access
* Use localStorage, sessionStorage, IndexedDB for persistence
* **Hard:** Synchronizing everything when you come back online

===

<h1 class="huge">The Hard Stuff<sup><small>TM</small></sup></h1>

---

## `_escaped_fragment_=`
# Search Engine Friendliness

---

# Data Security
## Users running arbitrary code. What could go wrong?

---

# Mobile Latency
## Mo Requests, Mo Problems.

===

<h1 class="huge">Static App Services</h1>

---

# Back-end Services
## Firebase, Parse, Kinvey

---

# Authentication Services
## UserApp.io, OAuth.io

---

# Hosting Services
## Divshot, S3, GitHub Pages

---

<h1 class="huge">Don't host static apps on Heroku</h1>

===

<h1 class="huge">Resources</h1>

* [**StaticApps.org:**](http://www.staticapps.org) resource site and newsletter for static apps
* [**Static Showdown:**](http://www.staticshowdown.com) static app hackathon (check out the winners!)
* [**divshot/superstatic:**](https://github.com/divshot/superstatic) static server powering Divshot hosting
* [**divshot/quick-deck:**](https://github.com/divshot/quick-deck) Reveal.js precompiler (how I made this deck)
* [**mbleigh/decks:**](https://github.com/mbleigh/decks) the source for my personal decks