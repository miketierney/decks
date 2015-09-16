---
title: "Extending Elements for Fun and Profit"
theme: /css/material.css
---

## **Extending Elements**
## For Fun and Profit

<br>**Web Components LA**  
August 27, 2014 / Michael Bleigh

<br>**decks.mbleigh.com/extending-elements**

===

# Inheritance
## **It's Object-Orientastic!**

---

```ruby
class Animal
  attribute_accessor :color
end

class Dog < Animal
  def call
    come_running!
  end
end

class Cat < Animal
  def call
    nil
  end
end
```

---

# A **is a** B

---

# Composition
## **It's...Composable?**

---

```html
<polymer-element name="much-compose">
  <template>
    <button>It's a Button</button>
    <p>And something else</p>
  </template>
</polymer-element>
```

===

## Composition is Better
### **(Most of the Time)**

---

# So When to Extend?

---

### When you want to get specific.

---

### When you need to work with native elements.

===

### Extending Polymer Elements

```html
<polymer-element name="cool-element" attributes="name">
  <template>
    {{name}} is so cool
  </template>
</polymer-element>

<polymer-element name="uncool-element" extends="cool-element">
  <template>
    <shadow></shadow>...not!
  </template>
</polymer-element>
```

---

# **`<shadow>`**
### Brings in Parent Shadow DOM

---

## Inheritance is **`super()`**

---

```html
<polymer-element name="parent-el">
  <script>
    Polymer('parent-el', {
      doSomething: function(a, b, c) {
        // ...
      }
    });
  </script>
</polymer-element>

<polymer-element name="child-el" extends="parent-el">
  <script>
    Polymer('child-el', {
      doSomething: function() {
        super(arguments);
        // ... and a bit more
      }
    })
  </script>
</polymer-element>
```

===

# In Action!
## **Action! Action!**

---

### **`<github-request>`**
### [ele.io/mbleigh/github-request](https://ele.io/mbleigh/github-request)

---

### **`<time is="strf-time">`**
### [ele.io/mbleigh/strf-time](https://ele.io/mbleigh/strf-time)

===

# Questions?
## **@mbleigh / @divshot**