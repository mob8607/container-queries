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

<v-clicks>

- What is it?
- Can I eat it?
- What took them so long?

</v-clicks>

---

# Hello

- I'm Mathias Ober
- Frontend Developer > 10 years
- Working at valantic
- X / Twitter: **@_omat** 👨‍💻 or **@SkyKartoffel** 🎮
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

Sometime around 2010 AD:

<v-clicks>

Web devs:
**We want to do responsive stuff dependant on screen size!**
<br>
Browser devs: 
_**Sure, here we got you media queries.**_
<br>
Web devs: 
**Noice, cool, thx bro.**

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


<v-clicks>

Web devs: **Quick question, how can we make stuff responsive to their container?**<br>

Browser devs: _**... about that... Nope, not gonna happen. Simply not possible.**_

Web devs:

</v-clicks>

<style>
p {
text-align: left;
    width: 100%;
}
</style>

---

<img src="/sad.gif" class="main-image" />

---

# But why?

- Basic principles of how browser layout works
- Every box has an intrinsic size
  - The content defines the size of the box
- Some boxes have an extrinsic size
  - The context defines the size of the box
  - User sets width for component

---

# Why not?

<img src="/code-element-queries.png" style="margin: auto;">

<img src="/text-no-container-queries.png" style="margin: auto;">

<span style="font-size: 16px;">
https://css-tricks.com/container-queries-once-more-unto-the-breach/
</span>

---

... years went by and developers dealt with those limitations, everyone was living their life and people forgot what they really wanted.

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

<img src="/tada.gif" class="main-image" style="width: 40vw;">

---

[Coding Time 03](https://codepen.io/mob6807/pen/PoXOzbq?editors=1100)

---

<img src="/caniuse.png" class="main-image">

There is a polyfill for older versions of the supported browsers

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
- CSS property `contain` tells browsers how to render specific elements
  - You can set `layout`, `size`, `paint`, `content`, or `none`
- `container-type`: `inline-size` or `size`
  
---

# Things to keep in mind

- Some of the default behavior changes for containers
  - `position: fixed` now reacts to the defined container
  - Changes how content is handled
- Container can't query themselves
- You can't change what you query
- Grid: Don't query the grid container -> add wrapper for each element to measure

---
 
# Container

- Container query looks for the nearest ancestor
- Container can have a name (or multiple)
- Range syntax for container queries (now also for media queries)

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

- `cqw, cqh, cqi, cqb, cqmin, cqmax` -> Same as viewport units but for containers.
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

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
<div>

```css
button .small-text, button .full-text {
  display: none;
}

@container (width > 220px) {
  button .full-text {
    display: inline;
  }
}

@container (100px < width < 220px) {
  button .small-text {
    display: inline;
  }

  button .full-text {
    display: none;
  }
}
```

</div>

<div style="display: grid;">
<img src="/button1.png" style="margin: auto;">

<img src="/button2.png" style="margin: auto;">

<img src="/button3.png" style="margin: auto;">
</div>
</div>

[Coding Time: Button](https://codepen.io/mob6807/pen/gOZXGmB)<br>
[Coding Time: Grid](https://codepen.io/mob6807/pen/poqdbRw)

---

# What's next

- Queries on style (custom properties) of the container (Chromium only)
  - `@container style(--colors: invert)`
  - No containment required (every element is a style query by default)
- Hopefully, but not confirmed:
  - Queries on normal style properties
  - Is a sticky element currently snapped?
  - and so on
  
---

# Thanks to 

- Miriam Suzanne for the inspiration 
- Patric Eberle for the motivation and help with the talk
- valantic and vlbgWebDev for hosting the event
- you for listening

