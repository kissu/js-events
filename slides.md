---
theme: default
drawings:
  persist: false
mdc: true
transition: fade-out

fonts:
  sans: Robot
  serif: Robot Slab
  mono: Fira Code
---
<Anime />

---

# Let's start by the Web platform 🌐

<v-clicks>

- SPA in your browser
- Web components
- Node.js server
- Hybrid Rendering
- Regular static bundled app
- Edge
- hosted on a pi0?!
- self-host ❤️‍🩹

</v-clicks>

<!--
Vue + Nuxt is quite open as of where you want to host it
💖

SPA:
  - easy to plug to anything thanks to the CDN approach, wire to Wordpress
  - can even be used for HomeAssistant if you're into home automation

Web components
💖
- syntax of SFC is close to modern HTML/CSS/JS 👉🏻 easy to transform into web components on a bigger scale (with micro-frontends at a big bank for example)

- NODE: perfect if you want some SSR content changing often
- HYBRID RENDERING: perfect if you want to fine-grain the behavior of all the possible variants 💖
- STATIC: Surge, Netlify, Vercel, Cloudflare pages
- EDGE 💖 closer to the user, interesting details closer to location of the user (decreased latency, shorter cold start boot times, a/b testing, geolocation)
- HOSTED on a pi0 💖
- SELF-HOST: no vendor lock-in, no limitations either, host where you want it! 🕊️💖
-->
---

# Web-ish platform

<v-clicks depth="2">

- PWAs to save the day! 🎊
- lowest effort for maximum output:
  - offline mode available
  - splitting context
  - perfect for webapps
  - [etc...]

</v-clicks>

<!--
plenty of Web platform and it's quite cool indeed but...
not the best support on all devices but mostly works out of the box

💖

[Show YouTube Music + Squoosh + Volta]
-->
---

# Desktop apps

<v-clicks depth="2">

- Web is cool and all but...we need more
- Tauri saves the day! 🥇
  - lots of security baked-in
  - frontend independent
  - minimal size for the bundle size
  - memory consumption is not growing like crazy

</v-clicks>

<!--
not enough? let's build a desktop app

ships less potential DRUGS lol bugs to the end user (checks the version of the browser all the time)

can use any kind of JS framework

because no need for Chromium, it's using the native web renderer

because we are all sick of using Electron with Slack, Discord, Teams

[💖 then show project ❤️‍🩹]
-->
---
layout: center
---

<h1 class="text-3xl">Btw, those slides are also using Vue.js 💚</h1>

<!-- Hello there 😉 -->

---

# Web Extension

<v-clicks depth="2">

- browser realm with still some interactivity?
- Google Manifest v3
- any benefits to Vue here?

</v-clicks>

<!--
lots of boilerplate, let's skip it

yes, because you can use the entire ecosystem with:
  - all VueUse composables
  - fine-grain reactivity
  - all the ecosystem/plugins

[show extension ❤️‍🩹]
-->

---

# Mobile app

<v-clicks depth="2">

- Ionic/Capacitor is the way to go nowadays
- why even use Nuxt here either? 🤔
- now, time for a hot take! 🔥 🌶️ 🧄 🫚 🔥

</v-clicks>

<!--
nice tool to bundle it all: Capacitor 💖
- nice cuz can be sent to any wearable
- TV OS is also a possible target
- or even embedded devices like car dashboards

plugins made by the Vue community 💖

the entire work from the Vue/Vite/Nuxt team is meant to be open and enable people to ship projects thanks to open source work

not owned by any company that could put any pressure on some decision-making regarding the direction of those frameworks

[showcase the app ❤️‍🩹]

🔥🔥🔥

have a big business and want to be serious? stop stacking JavaScript
use better/more specific tools like Flutter 💖


hire some iOS/Android/etc devs because at the end of the day, you still need to know the platform
-->

---
layout: center
---

<p class="text-4xl">🍉 Thanks 🙏🏻</p>
