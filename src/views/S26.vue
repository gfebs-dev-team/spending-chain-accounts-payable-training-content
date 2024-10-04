<script setup>
import { SlideSection } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount } from 'vue'

const slideData = {
  title: 'Payment Program Section III',
  sectionNum: 'Section III',
  subtitle: 'Payment Program',
  section: 'Payment Program',
  type: 'section'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 25)
})
</script>

<template>
  <SlideSection v-bind="slideData" />
</template>
