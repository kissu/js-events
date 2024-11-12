<template>
  <div class="flex items-center welcome">
    <!-- <h1 @click="showSvg = showSvg === false ? true : false" class="flex flex-col items-center justify-center h-full"> -->
      <img src="/uwu.png" class="h-full w-[35rem]" />
      <!-- <p class="events text-[7rem] text-[#42b883] font-light -mt-4">VueJS</p> -->
      <div class="js text-[3.5rem] text-[#f6aa1c]">5+ platforms</div>
    <!-- </h1> -->
  </div>
</template>

<script setup>
// import { ref, onMounted } from 'vue'
// import anime from 'animejs'
// import { useSound } from '@vueuse/sound'
// import sound from '../sounds/scribble.mp3'

// const showSvg = ref(false)
// const { play } = useSound(sound)
// let timeline

// onMounted(() => {
//   // identify the button to restart the animation
//   const button = document.querySelector('button');

//   // animate the prescribed nodes in sequence
//   timeline = anime.timeline({
//     easing: 'linear',
//     // as the animation begin remove the button by adding the prescribed class
//     begin: () => null,
//     // as the animation is completed, show the button
//     complete: () => button.classList.remove('hidden')
//   });

//   // show the x character
//   timeline.add({
//     targets: '.start',
//     strokeDashoffset: [anime.setDashoffset, 0],
//     duration: 250,
//   })

//   // show the dashed line
//   timeline.add({
//     targets: '.in-between',
//     strokeDashoffset: [0, anime.setDashoffset],
//     duration: 800,
//   })

//   // ping, show the goalpost icon
//   timeline.add({
//     targets: '.end',
//     rotate: [20, 0],
//     opacity: [0, 1],
//     easing: 'easeOutBounce',
//     duration: 300,
//   })
// });

// function restartAnimation() {
//   timeline.restart()
//   play()
// }
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400..700&family=Sacramento&family=Shantell+Sans:ital,wght@0,300..800;1,300..800&display=swap');
@import url("https://fonts.googleapis.com/css?family=IBM+Plex+Mono:500&display=swap");

.welcome svg {
  display: block;
  height: 100%;
}

.welcome button {
  font-family: inherit;
  border: none;
  border-radius: 5px;
  background: #242539;
  color: #4dc498;
  text-shadow: 0 1px 5px hsla(0, 0%, 0%, 0.1);
  padding: 0.5rem 1rem;
  margin: 1rem;
  font-size: 1.1rem;
  transition-property: opacity, visibility, transform;
  transition-duration: 0.25s;
  transition-timing-function: cubic-bezier(0.645, 0.045, 0.355, 1);
}

.hidden {
  opacity: 0;
  visibility: hidden;
  transform: translateY(-20px);
}

.welcome .fancy {
  font-family: Sacramento, cursive;
}


.slidev-page {
  /* background-color: #faedcd; */
  background-color: #1b4965;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
