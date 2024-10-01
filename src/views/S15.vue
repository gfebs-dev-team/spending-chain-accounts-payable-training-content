<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/demonstration.svg'

const slideData = {
  title: 'MIRO Create Invoice: Demo',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 14)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>Now you have the opportunity to view how to create an Invoice ia MIRO.</p>
    <p><span class="font-bold">Click</span> the icon on the right to begin.</p>
    <template #column_2>
      <a href=""><img :src="chart" className="h-full p-12" /></a>
    </template>
  </SlideColumns>
</template>
