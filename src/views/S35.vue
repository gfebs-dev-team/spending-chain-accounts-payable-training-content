<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/demonstration.svg'

const slideData = {
  title: '',
  type: 'content',
  section: 'Invoice Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 34)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <template #column_2>
      <img :src="chart" className="h-full p-12" />
    </template>
  </SlideColumns>
</template>
