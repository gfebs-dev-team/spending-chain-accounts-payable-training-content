<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 7',
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
  addSlide(slideData, 33)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question>
      Electronic Funds Transfer (EFT) information in the Vendor Master Data is updated via the
      Corporate Electronic Funds Transfer (CEFT) interface prior to payment.
    </template>
    <template #options>
      <SlideQuestionInput value="true" label="True" index="1" count="7" />
      <SlideQuestionInput value="false" label="False" index="2" count="7" />
    </template>
  </SlideQuestion>
</template>
