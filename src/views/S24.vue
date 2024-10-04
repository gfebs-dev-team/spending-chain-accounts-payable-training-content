<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 6',
  type: 'question',
  section: 'Invoicing Process',
  viewed: false,
  answer: 'true',
  user: ''
}

const slides = useSlidesStore()
const { addSlide } = slides

const answer = ref()
const checked_el = ref(0)

provide('answer', answer)
provide('checked_el', checked_el)

onBeforeMount(() => {
  addSlide(slideData, 23)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question>
      Miscellaneous Payment invoices are processed by the Invoice Processor at DFAS.
    </template>
    <template #options>
      <SlideQuestionInput value="true" label="True" index="1" count="6" />
      <SlideQuestionInput value="false" label="False" index="2" count="6" />
    </template>
  </SlideQuestion>
</template>
