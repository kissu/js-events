---
theme: default
drawings:
  persist: false
mdc: true
transition: fade-out
---
<Anime />

---

# Let's start simple 🌱


````md magic-move
```html
<button>click me now!</button>
```

```html
<button onclick="alert('Click!')">click me now!</button>
```
````

<button v-click class="px-4 py-2 font-bold border-2 bg-slate-100 text-slate-700 border-slate-500 rounded-xl" onclick="alert('Rolling! 🚌')">Oh yeah! 🤘🏻</button>

<div
  v-click
  v-motion
  :initial="{
    opacity: 1,
    rotate: -20,
    scale: 2,
    x: -80
  }"
  :enter="{
    opacity: 1,
    rotate: 10,
    scale: 1,
    x: 40,
    y: -50,
    transition: {
      duration: 1000,
    },
  }"
>
<fluent-emoji-cross-mark class="absolute text-7xl" />
</div>

<br />


<p v-click class="font-bold text-orange-400">Bad practice because:</p>

<v-clicks>

- not scalable: imagine with 345 buttons 🥹
- bloated HTML 🍔
- not secure at all 🦊

</v-clicks>

<!--
- basic HTML? yes...but not cuz
  - not scalable: 345 buttons with same event
  - bloated HTML
  - not secure either
-->

---
transition: slide-up
---

# How about something cleaner? 🧑‍💻

<main class="flex justify-around">

<div class="left-side">

````md magic-move
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="./style.css">
</head>

<body>
  <button>hello</button>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="./style.css">
</head>

<body>
  <button class="select-me">hello</button>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="./style.css">
</head>

<body>
  <button class="select-me">hello</button>

  <script src="./script.js"></script>
</body>
</html>
```
````

</div>

<div class="right-side" v-click="3">

````md magic-move
```js
console.log('works well')
```

```js
// double-check that the file is properly loaded
console.log('works well')
```

```js
// double-check that the file is properly loaded
console.log('works well')
// select the element and store it into a variable
const button = document.querySelector('.select-me')
```

```js
// double-check that the file is properly loaded
console.log('works well')
// select the element and store it into a variable
const button = document.querySelector('.select-me')
// add the listener to it
button.addEventListener('click', () => {
  console.log('Rocket shipped!! 🚀')
})
```

```js {5-8|9-10|*}
// double-check that the file is properly loaded
console.log('works well')
// select the element and store it into a variable
const button = document.querySelector('.select-me')
// move it to a function
function shipRocket() {
  console.log('Rocket shipped!! 🚀')
}
// add the listener to it 🕵🏻‍♂️
button.addEventListener('click', shipRocket)
```

```js
// double-check that the file is properly loaded
console.log('works well')
// select the element and store it into a variable
const button = document.querySelector('.select-me')
// move it to a function
function shipRocket() {
  console.log('Rocket shipped!! 🚀')
}
// add the listener to it 🕵🏻‍♂️
button.addEventListener('click', shipRocket)
// done working with it? clean up the memory usage 🧹
button.removeEventListener('click', shipRocket)
```
````

</div>

<v-clicks>

</v-clicks>

<!--
showcase:
- usage of $0
- getEventListeners($0)
- devtools: Elements -> Event listeners
- `event` object
- DOMContentLoaded
- event + keypress + event.key + keycode.info
  - make a function with it + `console.log`
- showcase `this` in a function
-->

</main>

<p v-click class="pt-12 text-2xl text-center">Let's see this in action + the <code>event</code> object. 👨🏻‍💻</p>

---

```js
element.addEventListener(event, handler, [options]);
```

<Arrow v-click x1="200" y1="150" x2="250" y2="80" color="orange" />
<Arrow v-click="2" x1="325" y1="300" x2="320" y2="80" color="turquoise" />
<Arrow v-click="3" x1="600" y1="250" x2="400" y2="80" color="fuchsia" />

<p class="absolute pt-16 text-2xl triggers" v-click="1">This is the trigger
<br /><span class="text-base text-lime-400 element">- click</span>
<br /><span class="text-base text-lime-400 element">- keypress</span>
<br /><span class="text-base text-lime-400 element">- mouseover</span>
<br /><span class="text-base text-lime-400 element">- submit</span>
<br /><span class="text-base text-lime-400 element">- focus</span>
<br /><span class="text-base text-lime-400 element">- blur</span>
<br /><span class="text-base text-lime-400 element">- transitionend</span>
</p>

<p class="absolute text-2xl pt-[14rem] pl-[14rem]" v-click="2">Your callback function
<br /><span class="text-base"><code>ie. shipRocket</code></span>
</p>

<p class="absolute text-2xl pt-[11rem] pl-[34rem]" v-click="3">[Optional] options object
<br /><span class="text-base text-pink-300">- capture</span>
<br /><span class="text-base text-pink-300">- once</span>
<br /><span class="text-base text-pink-300">- passive</span>
<br /><span class="text-base text-pink-300">- signal</span>
</p>


---

# Few other examples of triggers (Gamepad API)

<GamepadDemo />

---

## Intersection Observer API

<Intersection />

---
dragPos:
  square: [ 800, 100, 200, 50 ]
---

# Draggable elements

<img class="!w-96" v-drag="[448,64,400,400,37]" src="https://www.lewagon.com/assets/v4/logo-lewagon-9c19fb39a748cd3b1f49059ce0dc6c0dfc4cc2447d5a9a3e01bd2d5a214faf3c.svg">

---
transition: slide-up
---

<!--
plenty of other ones:
- dropzone
- resize
-->

## There are <span v-mark.circle.red="1">plenty</span> more!

<p v-click="2">Few interesting links:</p>

<ul v-click="3">
<li><a href="https://gorescript.github.io/classic/play/">Gorescript</a></li>
<li><a href="https://developer.mozilla.org/enUS/docs/Web/Events">Event reference on MDN</a></li>
<li><a href="https://javascript.info/introduction-browser-events">javascript.info</a></li>
<li><a href="https://javascript.info/bubbling-and-capturing">[optional] Bubbling</a></li>
</ul>

---

# Slides available on Github

[kissu/js-events](https://github.com/kissu/js-events)

## And hosted on Netlify

[lw-events.netlify.app](https://lw-events.netlify.app/1)
