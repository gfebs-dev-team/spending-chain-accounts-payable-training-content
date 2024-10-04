<script setup>
import { SlideCheckpoint } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import checkpoint from '@/assets/img/module_checkpoint.png'

const slideData = {
  title: 'Learning Checkpoint',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 17)
})
</script>

<template>
  <SlideCheckpoint v-bind="slideData" :columns="1" :image="checkpoint">
    <p>
      Before we summarize the topics in the Invoicing section, it's important to check your
      knowledge of the material covered. This is your opportunity to ensure you are understanding
      the course material.
    </p>
    <p>Proceed to answer six questions to test your understanding of the material covered.</p>
  </SlideCheckpoint>
</template>
