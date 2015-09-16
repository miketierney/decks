---
title: Static Web Rising
theme: /css/static-web-rising.css
---
! data-background="#fc0"

# Static Web Rising
## Michael Bleigh

### OSCON 2014 &mdash; Portland, OR

decks.mbleigh.com/static-web-rising

===

# About This Talk

---

# Wide but Shallow
## So many topics, so little time

---

# Office Hours!
## 1:40pm Today, O'Reilly Booth

===

# Static Web

---

<img src="/images/what-does-it-mean.gif" alt="What does it mean?" height="600" width="600">

---

### **static:** lacking in movement, action, or change, especially in a way viewed as undesirable or uninteresting.

---

# Yikes.

---

# This, right?

![Ugly Site](/images/geocities-site.jpg)

---

# Not Quite.

---

# Single-Page Apps?

---

# Not Quite.

---

# noBackend?

---

# Not Quite.

---

### Any web site where files are served to the browser **without server-side modification**.

---

## In Other Words:<br>**HTML, JS, and CSS**

===

# Why Static?

---

# Talent Pool
## Everybody knows HTML/JS

---

# Scale Simpler
## It's just files

---

# Modularity
## Better Architecture Sooner
---

# Flexibility
## Fungible UX

---

# Intangibles
## It *feels* right.

===

# Why Now?

---

# Better Browsers
### CORS, Web Components, Offline, Service Workers

---

# Better Tools
## Jekyll, Angular, Karma

---

# Better Platforms
## IaaS to PaaS to BaaS

---

# Better Crawlers
## Google. Crawls. JavaScript!

===

# Types of<br>Static Apps

---

# <s style="color: red;">Single-Page Apps</s>

---

# Web Clients

* Content fetched and rendered by JavaScript
* Typically one HTML file for whole app
* Frameworks like Angular, Ember, Backbone

---

# Packaged Clients

* Subset of Web Clients
* Chrome Extensions, Cordova, Offline Apps
* "Installed" vs. Requested

---

# Compiled Sites

* Take data (usually files), turn into flat HTML
* Best for low-interaction, high-content sites
* Jekyll, Metalsmith, Middleman, Etc.

===
! data-background="#911" class="dark"

# Enough Definitions

---
! data-background="#bf9"

# How do we<br>*build* stuff?

---

# Write HTML

```html
<!doctype html>
<html>
  <body>
    <h1>Hello, World</h1>
  </body>
</html>
```

---

# Put it on a Server

---

# You're Done.
## Any questions?

---

# Just Kidding.
## (Kind of)

===

# Browser Tech

---
! data-background="rgb(114, 191, 188)"

# CORS
## True Cross-Domain AJAX

---

# Client-Side

* Just make AJAX calls with a fully-qualified URL
* Browser handles everything else
* "Preflighting" Requests

---

# Server-Side

* Must set `Access-Control-*` headers
* Must listen for `OPTIONS` requests
* Just find a library for your language and use it

---

# Third Parties

* Some third-party APIs have explicit CORS support
* GitHub, Amazon Web Services, Etc.
* Serverless Mashups are **Awesome**

---

# Why it Matters

* Allows for completely separated interface and API
* Encourages browser as coordinating agent of services
* All the benefits of AJAX (even cookies!)

---
! data-background="rgb(114, 191, 188)"

# HTML5 Offline
## Server Apps Can't Do It

---

# Application Cache

* Lets you define paths to be cached offline
* Allows for "fallbacks"
* Works in desktop and mobile browsers
* Is [kind of a douchebag](http://alistapart.com/article/application-cache-is-a-douchebag)

---

## Implementing App Cache
See linked article for the (many) gotchas.

```html
<html manifest="offline.appcache">
```

```
CACHE MANIFEST
# v1
index.html
app.js
NETWORK:
*
FALLBACK:
/ index.html
/images/avatars/ images/default-avatar.png
```

---

# Web Storage

* **localStorage:** store key/value data local to the browser
* **sessionStorage:** store key/value data local to the tab
* **IndexedDB:** store structured data with a terrible API

---

## Web Storage in Practice

* Use **localStorage** sparingly, if at all. Only for small data
* Use **sessionStorage** for things like multiple logins
* Use **IndexedDB** (with a wrapper) for most storage needs
* I like Mozilla's [localForage](https://github.com/mozilla/localForage)

---

# Why it Matters

* Allows users to access data with bad connectivity, even offline
* Can't be done with traditional server request/response apps

---
! data-background="/images/futurama-bg.jpg"

<h1 style="text-shadow: 2px 2px 10px 6px black; color: white">In the Future...</h1>

---
! data-background="rgb(114, 191, 188)"

# Web Components
## Web as True App Platform

---

```html
<user-profile username="mbleigh"></user-profile>

<google-map location="Portland, OR"></google-map>

<ui-tabs>
  <ui-tab label="My Tab">
  </ui-tab>
</ui-tabs>
```

---

## Components of Web Components

* **HTML Imports:** Like a module loader for HTML
* **Template Tag:** Inert HTML that can be used by JavaScript
* **Shadow DOM:** Magical display and style encapsulation
* **Custom Elements:** Bring it all together

---

# Enormous Topic

I gave a three-hour workshop at Fluent and still barely scratched the surface
of how important and big this is.

---

## Getting Your Feet Wet

* Demos: [github-readme](https://ele.io/mbleigh/github-readme) or [gif-me](https://ele.io/collin/gif-me)
* [Polymer](http://www.polymer-project.org): Polyfills from Google plus framework
* [HTML5 Rocks](http://www.html5rocks.com/en/) has some good content too

---

# Why it Matters

* Makes front-end framework ideas native
* Built for developer productivity and utility
* Going to affect every aspect of web development

---
! data-background="rgb(114, 191, 188)"

# Service Workers
## Mind-Blowing Control

---

# What are they?

Service Workers are scripts that run **independently of web pages**. They can
intercept and manipulate incoming requests for a domain.

---

# What can they do?

* Replace (and improve) the Application Cache
* Allow for browser-native `pushState` routing
* Dynamically fetch and process non-HTML content
* Crazy, yet untold things

---

# Why it Matters

* Moves browsers away from request/response
* Moves capability from server to client
* Drastically increases flexibility

===

# Static Resistance

---

### "JavaScript apps have to load the page, then load the data and render it, so it's inherently slower than traditional web apps."

---

* For sites that depend on public external links...sometimes true.
* For apps that need login or have multiple interactions...never true.
* For content sites, consider static compilation
* For non-content sites, performance is likely be net gain

---

### "Before I just had one app. If I separate my front-end I'll have more to maintain."

---

* You already had two apps, they just shared a repo
* Separating early will help you think architecturally
* Try it. You'll like it.

---

### "Single-Page Apps don't get properly indexed by search engines."

---

* **Not anymore!** Google now crawls JavaScript
* Services like [Prerender.io](http://prerender.io) are available to help
* Static compiled sites work great for search engines

===

# Resources

---

* [StaticApps.org](http://www.staticapps.org): Resource site for all things static,
  content mostly written by me.
* [StaticGen.com](https://www.staticgen.com/): Giant list of static site generators
  if you're looking for one.
* [Divshot](http://www.divshot.com/): Static app Platform-as-a-Service hosting
  based on open-source [Superstatic](https://github.com/divshot/superstatic) server.
  
---

## [@mbleigh](http://twitter.com/mbleigh) on Twitter

I think about this stuff all day long. Ask me anything.

Also, remember there are **office hours<br>at 1:40pm today** in the O'Reilly booth.

Thanks!
