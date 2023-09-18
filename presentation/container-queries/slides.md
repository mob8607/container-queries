---
theme: seriph
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
---

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

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

# Container Queries

Sometimes in 2012:

<v-clicks>

Web devs: **We want to do responsive stuff dependant on screen size!**

Browser devs: _**Yeah, here you have media queries.**_

Web devs: **Nice cool, thx bro.**

<img src="/05.gif" style="margin: auto;" />


</v-clicks>

---

[Coding Time 01](https://jsfiddle.net/_omat/fga13m94/13/)

---

<v-clicks>

_Designer enters the game_

**Hey, our new design has a very cool sidebar. I made it easy for you, just use the same components as on the mobile version.**

</v-clicks>

---

[Coding Time 02](https://jsfiddle.net/_omat/f9h7ncmL/8/

---

<v-clicks>

Web devs: **Sorry to bother, but can we also make stuff responsive to the container?**

Browser devs: _**... about that... Sorry. Nope, not gonna happen. Not possible.**_

Web devs:
</v-clicks>
---

<img src="/01.gif" style="margin: auto;" />

---

<v-clicks>
End of story?

Browser devs: _**Remember about that thing you asked some time ago?**_
</v-clicks>

---

<div style="text-align: center; margin-top: 20px; font-size: 40px;">

**CONTAINER QUERIES**

</div>

<img src="/02.gif" style="margin: auto;">

---

<img src="/04.gif" style="margin: auto;">

---

[Coding Time 03](https://jsfiddle.net/_omat/f9h7ncmL/17/)

---

<img src="/03.gif" style="margin: auto;">

---

Did they lie to us?

TODO: Erklärung intrinsic sizing from browser.
container-types


---

Example with grid:

[Coding Time 04](https://jsfiddle.net/_omat/6wb8pxqd/10/)

---

