<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/accounts1.svg'

const slideData = {
  title: 'Welcome to Payment Program',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 26)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      After the invoice is successfully posted we get to the final step, the Payment Program. Let's
      take a look at what is discussed in this section of the lesson:
    </p>
    <ul class="list-disc pl-8">
      <li>Payment Process Roles</li>
      <li>Payment Process Key Terms</li>
      <li>Payment Program Process Flow</li>
    </ul>
    <template #column_2>
      <img :src="chart" className="px-12" />
    </template>
  </SlideColumns>
</template>
