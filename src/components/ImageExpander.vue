<script setup>
import { ref } from 'vue'

const toggleState = ref(false)

function toggleSize() {
  toggleState.value = !toggleState.value
}

defineProps(['src', 'className', 'alt'])
</script>

<template>
  <img @click="toggleSize" :src="src" :class="className" :alt="alt" />

  <Teleport to="body">
    <div
      v-if="toggleState"
      @click="toggleSize"
      class="bg-richblack bg-opacity-20 backdrop-blur-md w-full h-full absolute inset-0 z-10 p-20 flex items-center justify-center"
    >
      <img
        :src="src"
        class="contain h-auto w-auto object-center xl:max-w-[1200px]"
        :class="className"
        :alt="alt"
      />
    </div>
  </Teleport>
</template>
