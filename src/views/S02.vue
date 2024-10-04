<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import target from '@/assets/img/target.svg'

const slideData = {
  title: 'Objectives',
  type: 'content',
  section: 'Introduction'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 1)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <ul class="list-disc pl-4 flex flex-col gap-2">
      <li>Describe the steps involved in the Invoice Entry process</li>
      <li>List the types of invoices entered in GFEBS</li>
      <li>Describe how miscellaneous invoices differ from contractual invoices</li>
      <li>List the roles necessary for the Invoice Entry process to occur</li>
      <li>Summarize the procedures for processing blocked invoices</li>
    </ul>
    <template #column_2>
      <img :src="target" alt="target" class="px-8" />
    </template>
  </SlideColumns>
</template>
