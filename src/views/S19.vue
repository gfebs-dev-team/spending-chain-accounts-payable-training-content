<script setup>
import { SlideQuestion, SlideQuestionInput } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount, provide, ref } from 'vue'

const slideData = {
  title: 'Question 2',
  type: 'question',
  section: 'Invoicing Process',
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
  addSlide(slideData, 18)
})
</script>

<template>
  <SlideQuestion :title="slideData.title">
    <template #question>
      Which of the following is not a requirement for routing of a miscellaneous payment invoice:
    </template>
    <template #options>
      <SlideQuestionInput value="a" label=" Attach Support Documentation" index="1" count="2" />
      <SlideQuestionInput
        value="b"
        label="Choosing the Correct Document type"
        index="2"
        count="2"
      />
      <SlideQuestionInput
        value="c"
        label="Local Approval from the Misc Pay Approver"
        index="3"
        count="2"
      />
      <SlideQuestionInput
        value="d"
        label="DFAS Approval from the Misc Pay Approver"
        index="4"
        count="2"
      />
    </template>
  </SlideQuestion>
</template>
