<script setup>
import { SlideSection } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount } from 'vue'

const slideData = {
  title: 'Invoicing Process Section II',
  sectionNum: 'Section II',
  subtitle: 'Invoicing Process',
  section: 'Invoicing Process',
  type: 'section'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 2)
})
</script>

<template>
  <SlideSection v-bind="slideData" />
</template>
