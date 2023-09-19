---
theme: eloc
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
title: Welcome to Container Queries
mdc: true
canvasWidth: 1550
layout: center
---

# CONTAINER QUERIES


---
transition: fade-out
---

# Hello

- I'm Mathias Ober.
- Frontend Developer > 10 years
- Working at valantic
- X / twitter: **@_omat** 👨‍💻 or **@SkyKartoffel** 🎮
- Hobbies: 🎮 ⛵︎ 🏸 ⛷️ 🎤 🎸

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
layout: default
---

# 

Sometimes in 2012 AD:

<v-clicks>

Web devs:
**We want to do responsive stuff dependant on screen size!**
<br>
Browser devs: 
_**Sure, here we got media queries.**_
<br>
Web devs: 
**Nice cool, thx bro.**

<img src="/thumbsup.gif" style="margin: auto; width: 20vw;" />

</v-clicks>

---

[Coding Time 01](https://codepen.io/mob6807/pen/mdaqErb)

---

_Designer enters the game_

<v-clicks>

**We need a sidebar. Just use the existing mobile styling.<br> It's easy, right?**

</v-clicks>

---

<img src="/sweating.gif" class="main-image" />

---

[Coding Time 02](https://codepen.io/mob6807/pen/PoXOzbq?editors=1100)

---

<img src="/calculate.gif" class="main-image" />

---

Web devs: **Quick question, how we also make stuff responsive to their container?**

<v-clicks>

Browser devs: _**... about that... Nope, not gonna happen. Not possible.**_

Web devs:

</v-clicks>

---

<img src="/sad.gif" class="main-image" />

---

# But why?

- Basic principles of how browser layout works.
- Every box has an intrinsic size. 
  - The content defines the size of the box.
- Some boxes have an extrinsic size. 
  - The container defines the size of the box.

---

# Why not?

<img src="/code-element-queries.png" style="margin: auto;">

<img src="/text-no-container-queries.png" style="margin: auto;">

<span style="font-size: 16px;">
https://css-tricks.com/container-queries-once-more-unto-the-breach/
</span>

---

... years went by and developers dealt with those limitations, everyone was living his life and people forgot what they really wanted.

---

The END

---

... until 2022 ...

<v-clicks>

Browser devs: _**Remember about that thing you asked some time ago?**_

</v-clicks>

---

<div style="text-align: center; margin-top: 20px; font-size: 40px;">

**CONTAINER QUERIES**

</div>

<img src="/tada.gif" class="main-image" style="width: 50vw;">

---

[Coding Time 03](https://codepen.io/mob6807/pen/PoXOzbq?editors=1100)

---

<img src="/caniuse.png" class="main-image">

---

<img src="/minions.gif" class="main-image" alt="minions">

---

<img src="/timeout.gif" class="main-image">

<v-clicks>

Did they lie to us?

</v-clicks>

---

# What happened?

<img src="/text-solution.png" class="main-image">

<span style="font-size: 16px;">
https://css-tricks.com/container-queries-once-more-unto-the-breach/
</span>

---

# Limitations

- You need to define what you want to query from a container
- As a developer we need to create explicit containers to measure them
- Some of the default behavior changes for containers
  - `position: fixed` reacts now to the defined container
  - Box model changes
  
---

# Container

- CSS property `contain` tells browsers how to render specific elements
  - You can set layout, size, paint, content, or none
- `container-type`: `inline-size` or `size`
- Container can't query themselves
- You can't change what you query
- In grid you can't query the space the item would take -> you need to add a container for each element to measure.

---

- polyfill for older versions of the current browsers
- Finding container query the nearest ancestor
- container can have a name (or multiple)
- range syntax for container queries (and media queries now)

```css

.sidebar {
  container-type: inline-size;
  container-name: sidebar;
}

@container sidebar (50px < width < 380px) {
  .card {
    background-color: red;
  }
}

```

---

# Container Query Units

- cqw, cqh, cqi, cqb, cqmin, cqmax -> Same as viewport units but for containers.
- Can be used for animations

<!--
cqw: 1% of a query container's width
cqh: 1% of a query container's height
cqi: 1% of a query container's inline size
cqb: 1% of a query container's block size
cqmin: The smaller value of either cqi or cqb
cqmax: The larger value of either cqi or cqb
-->

---

# Examples

```css
@container (width > 220px) {
  button span.full-text {
    display: inline;
  }
}

@container (100px < width < 220px) {
  button span.small-text {
    display: inline;
  }

  button span.full-text {
    display: none;
  }
}
```

[Coding Time 04](https://codepen.io/mob6807/pen/poqdbRw)

---

# What's next

- Queries on style (custom properties) of the container
  - `@container style(--colors: invert)`
  - No containment required (Every element is a style query by default)
  - Is a sticky element currently snapped?
  - Currently only on chromium browsers in experimental mode
- Hopefully, but not confirmed:
  - Queries on normal style properties
---

# Thanks to 

- Miriam Suzanne for the inspiration 
- Patric Eberle for the motivation and help with the talk
- valantic for hosting the webdev
- you for listening

---
