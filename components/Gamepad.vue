<script setup lang="ts">
import { computed } from 'vue-demi'
import Item from './Item.vue'
import Controller from './Controller.vue'

const props = defineProps<{ gamepad: Gamepad }>()

const supportsVibration = computed(() => props.gamepad?.hapticActuators?.length > 0)
function vibrate() {
  if (supportsVibration.value) {
    const actuator: any = props.gamepad.hapticActuators[0]
    actuator.playEffect('dual-rumble', {
      startDelay: 0,
      duration: 1000,
      weakMagnitude: 1,
      strongMagnitude: 1,
    })
  }
}
</script>

<template>
  <div bg="dark:dark-500 light-100" shadow="~ md" border="rounded" max-w="screen-sm" mx="auto" overflow="hidden"
    grid="~" class="grid-cols-[2fr,1fr]">
    <button @click="vibrate">vibrate</button>
    <template v-if="gamepad.mapping === 'standard'">
      <Controller :gamepad="gamepad" text="dark-100 opacity-70 dark:(light-900 opacity-70)" />
    </template>
    <template v-else>
      <span font-medium text="dark:(light-900 opacity-70)">
        Unknown Controller Type
      </span>
    </template>
  </div>
</template>
