<template>
  <div class="flex items-center welcome gap-x-6">
    <h1 @click="showSvg = showSvg === false ? true : false" class="flex flex-col items-center justify-center h-full">
      <div class="js text-[6rem] text-[#f6aa1c]">Javascript</div>
      <div class="events text-[5rem] text-white font-light -mt-4">Events</div>
    </h1>

    <Transition>
      <svg viewBox="0 0 100 100" v-show="showSvg" @mouseleave="restartAnimation">
        <rect width="100" height="100" rx="2" fill="#242539" />
        <g fill="none" stroke="#4DC498" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <!-- dashed trail -->
          <g transform="translate(20 35)">
            <path d="M 0 0 v 25 h 15 l 10 -15 h 10 v 20 h 25" stroke-dasharray="3 6" stroke-dashoffset="2" />
            <!-- animate the dash of a line atop the already dashed line -->
            <path class="in-between" stroke="#242539" stroke-width="2.5"
              d="M 60 30 h -25 v -20 h -10 l -10 15 h -15 v -25" />
          </g>

          <!-- include the x character atop the dashed trail -->
          <g transform="translate(20 35)">
            <!-- duplicate the path element describing the x sign to animate the segments in sequence -->
            <path class="start" d="M -3 -3 l 6 6" />
            <path class="start" d="M 3 -3 l -6 6" />
          </g>

          <!-- goalpost icon -->
          <g transform="translate(80 65)">
            <!-- position the group by rotating the shape from a point on the right side -->
            <g transform="translate(40 20)">
              <g class="end">
                <g transform="translate(-40 -20)">
                  <path d="M 0 0 q 6 -6 6 -10 a 6 6 0 0 0 -12 0 q 0 4 6 10" />
                  <circle cy="-10" r="2" stroke="none" fill="#4DC498" />
                </g>
              </g>
            </g>
          </g>
        </g>
      </svg>
    </Transition>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import anime from 'animejs'
import { useSound } from '@vueuse/sound'
import sound from '../sounds/scribble.mp3'

const showSvg = ref(false)
const { play } = useSound(sound)
let timeline

onMounted(() => {
  // identify the button to restart the animation
  const button = document.querySelector('button');

  // animate the prescribed nodes in sequence
  timeline = anime.timeline({
    easing: 'linear',
    // as the animation begin remove the button by adding the prescribed class
    begin: () => null,
    // as the animation is completed, show the button
    complete: () => button.classList.remove('hidden')
  });

  // show the x character
  timeline.add({
    targets: '.start',
    strokeDashoffset: [anime.setDashoffset, 0],
    duration: 250,
  })

  // show the dashed line
  timeline.add({
    targets: '.in-between',
    strokeDashoffset: [0, anime.setDashoffset],
    duration: 800,
  })

  // ping, show the goalpost icon
  timeline.add({
    targets: '.end',
    rotate: [20, 0],
    opacity: [0, 1],
    easing: 'easeOutBounce',
    duration: 300,
  })
});

function restartAnimation() {
  timeline.restart()
  play()
}
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

.welcome .js {
  font-family: Montserrat, sans-serif;
  text-transform: uppercase;
}

.welcome .events {
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
