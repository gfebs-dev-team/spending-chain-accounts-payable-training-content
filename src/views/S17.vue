<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/demonstration.svg'

const slideData = {
  title: 'MIRO Create Invoice: Sim',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 16)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      Now is time to practice executing creating an Invoice via MIRO. You have the opportunity to
      practice tasks that you will perform in the GFEBS system by completing a scenario. When you
      open the simulation, you will be provided with instructions to properly execute the
      transaction.
    </p>
    <p><span class="font-bold">Role</span>: Site Invoice Processor, Invoice Processor</p>
    <p><span class="font-bold">Scenario</span>: Create Invoice</p>
    <p><span class="font-bold">Transaction Code</span>: MIRO</p>
    <p><span class="font-bold">Click</span> the icon on the right to begin.</p>
    <template #column_2>
      <a href=""><img :src="chart" className="h-full p-12" /></a>
    </template>
  </SlideColumns>
</template>
