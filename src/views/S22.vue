<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 5',
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
  addSlide(slideData, 21)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question>
      Who is responsible attaching supporting documentation to MISC Pay invoices using FB02?
    </template>
    <template #options>
      <SlideQuestionInput value="a" label="Site Invoice Processor" index="1" count="5" />
      <SlideQuestionInput
        value="b"
        label="Payment Interface Processing Monitor"
        index="2"
        count="5"
      />
      <SlideQuestionInput value="c" label="Payment Certifier" index="3" count="5" />
      <SlideQuestionInput value="d" label="Invoice Processor" index="4" count="5" />
    </template>
  </SlideQuestion>
</template>
