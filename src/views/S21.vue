<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 3',
  type: 'question',
  section: 'Invoicing Process',
  viewed: false,
  answer: 'a',
  user: ''
}

const slides = useSlidesStore()
const { addSlide } = slides

const answer = ref()
const checked_el = ref(0)

provide('answer', answer)
provide('checked_el', checked_el)

onBeforeMount(() => {
  addSlide(slideData, 20)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question> Which of the following roles inputs the Misc. Pay Invoices? </template>
    <template #options>
      <SlideQuestionInput value="a" label="Site Invoice Processor" index="1" count="3" />
      <SlideQuestionInput value="b" label="Payment Certifier" index="2" count="3" />
      <SlideQuestionInput
        value="c"
        label="Payment Interface Processing Monitor"
        index="3"
        count="3"
      />
      <SlideQuestionInput value="d" label="Payment Processor" index="4" count="3" />
    </template>
  </SlideQuestion>
</template>
