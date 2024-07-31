<script setup lang="ts">
import { useGamepad } from '@vueuse/core'
import Gamepad from './Gamepad.vue'

const { isSupported, gamepads } = useGamepad()
</script>

<template>
  <div>
    <div space="y-4">
      <Gamepad v-for="gamepad in gamepads" :key="gamepad.id" :gamepad="gamepad" />
    </div>
  </div>
</template>
