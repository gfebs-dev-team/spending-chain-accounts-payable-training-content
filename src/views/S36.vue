<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 8',
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
      During the Payment Run, the payment program is run separately for check and EFT payments and
      generates multiple files.
    </template>
    <template #options>
      <SlideQuestionInput value="true" label="True" index="1" count="8" />
      <SlideQuestionInput value="false" label="False" index="2" count="8" />
    </template>
  </SlideQuestion>
</template>
