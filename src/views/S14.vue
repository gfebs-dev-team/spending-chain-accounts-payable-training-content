<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/demonstration.svg'

const slideData = {
  title: 'FB60 Misc. Pay Invoice: Demo',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 13)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      Now that we've discussed the different types of invoices and their purpose, you have the
      opportunity to view the user interact with the GFEBS system.
    </p>
    <p><span class="font-bold">Click</span> the icon on the right to begin.</p>
    <template #column_2>
      <a href=""><img :src="chart" class="h-3/4 md:p-8 md:pt-0 object-contain mx-auto" /></a>
    </template>
  </SlideColumns>
</template>
