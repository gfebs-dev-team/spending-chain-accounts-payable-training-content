<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/accounts15.svg'

const slideData = {
  title: 'Summary',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 40)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>This concludes the Payment Program section.</p>
    <p>Now you should be able to perform the following:</p>
    <ul class="pl-8 list-disc">
      <li>Describe the Payment process</li>
      <li>Describe the key steps involved in the Payment process</li>
      <li>List the interfaces involved in the Payment process</li>
      <li>List the roles necessary for the Payment process to occur</li>
    </ul>
    <template #column_2>
      <img :src="chart" className="p-12" />
    </template>
  </SlideColumns>
</template>
