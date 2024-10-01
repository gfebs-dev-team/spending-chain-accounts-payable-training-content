<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 11',
  type: 'question',
  section: 'Payment Program',
  viewed: false,
  answer: 'd',
  user: ''
}

const slides = useSlidesStore()
const { addSlide } = slides

const answer = ref()
const checked_el = ref(0)

provide('answer', answer)
provide('checked_el', checked_el)

onBeforeMount(() => {
  addSlide(slideData, 37)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question> Which role is the final authority when processing payments? </template>
    <template #options>
      <SlideQuestionInput value="a" label="Payment Processor" index="1" count="11" />
      <SlideQuestionInput value="b" label="Payment Close Processor" index="2" count="11" />
      <SlideQuestionInput
        value="c"
        label="Payment Interface Processing Monitor"
        index="3"
        count="11"
      />
      <SlideQuestionInput value="d" label="Payment Certifier" index="4" count="11" />
    </template>
  </SlideQuestion>
</template>
