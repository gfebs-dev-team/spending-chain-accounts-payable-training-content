<script setup>
import { SlideSection } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount } from 'vue'

const slideData = {
  title: 'Review Section IV',
  sectionNum: 'Section IV',
  subtitle: 'Review',
  section: 'Lesson Review',
  type: 'section'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 41)
})
</script>

<template>
  <SlideSection v-bind="slideData" />
</template>
