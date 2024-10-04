<script setup>
import SlideColumns from './Columns.vue'
import checkpoint from '@/assets/img/checkpoint.svg'
defineProps(['slideData', 'image'])
</script>
<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <slot />

    <template #column_2>
      <img class="md:p-8 md:pt-0 object-contain w-full h-full" :src="checkpoint" />
    </template>
  </SlideColumns>
</template>
