<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import target from '@/assets/target.svg'

const slideData = {
  title: 'Objectives',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 27)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <ul class="list-disc pl-8 flex flex-col gap-4">
      <li>Describe the Payment process.</li>
      <li>Describe the key steps involved in the Payment process.</li>
      <li>List the interfaces involved in the Payment process.</li>
      <li>List the roles necessary for the Payment process to occur.</li>
    </ul>
    <template #column_2>
      <img :src="target" alt="target" class="px-8" />
    </template>
  </SlideColumns>
</template>
