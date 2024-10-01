<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 12',
  type: 'question',
  section: 'Payment Program',
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
  addSlide(slideData, 38)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question>
      What determines which disbursing system, ADS or DDS, should be used to process the payment?
    </template>
    <template #options>
      <SlideQuestionInput value="a" label="The PMS field on the invoice" index="1" count="12" />
      <SlideQuestionInput value="b" label="Vendors Name" index="2" count="12" />
      <SlideQuestionInput value="c" label="Cost Object on the Invoice" index="3" count="12" />
      <SlideQuestionInput value="d" label="None of the Above" index="4" count="12" />
    </template>
  </SlideQuestion>
</template>
