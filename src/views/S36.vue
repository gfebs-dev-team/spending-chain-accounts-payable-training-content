<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 9',
  type: 'question',
  section: 'Payment Program',
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
  addSlide(slideData, 35)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question>
      The Automated Disbursing System (ADS) is an extemal payment system which interfaces with GFEBS
      in the Payment Process:
    </template>
    <template #options>
      <SlideQuestionInput value="true" label="True" index="1" count="9" />
      <SlideQuestionInput value="false" label="False" index="2" count="9" />
    </template>
  </SlideQuestion>
</template>
