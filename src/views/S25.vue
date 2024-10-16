<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/accounts15.svg'

const slideData = {
  title: 'Summary',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 24)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>This concludes the Invoice section.</p>
    <p>The following are tasks that you should be able to perform:</p>

    <ul class="list-disc pl-8">
      <li>Describe the steps involved in the Invoice Entry process</li>
      <li>List the types of invoices that can be entered into GFEBS</li>
      <li>Describe how miscellaneous invoices differ from contractual invoices</li>
      <li>List the roles necessary for the invoice entry process to occur</li>
      <li>Summarize the procedures for processing blocked invoices</li>
    </ul>
    <template #column_2>
      <img :src="chart" className="h-full p-12" />
    </template>
  </SlideColumns>
</template>
