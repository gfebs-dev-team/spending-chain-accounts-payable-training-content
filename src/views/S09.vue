<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import image from '@/assets/img/demonstration.svg'

const slideData = {
  title: 'MIR4 Display Contract Invoice: Demo',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 8)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      The purpose of this demonstration is to display a contractual invoice in GFEBS. The simulated
      environment provides an opportunity to view tasks that you will perform in GFEBS.
    </p>
    <p><span class="font-bold">Click</span> the icon on the right to begin.</p>
    <template #column_2>
      <a href="#"><img :src="image" className="h-full px-12" /></a>
    </template>
  </SlideColumns>
</template>
