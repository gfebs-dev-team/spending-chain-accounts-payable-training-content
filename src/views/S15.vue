<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/demonstration.svg'

const slideData = {
  title: 'FB60 Misc. Pay Invoice: Sim',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 14)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      Now is time to practice executing a Misc Pay Invoice via FB60. You have the opportunity to
      practice tasks that you will perform in the GFEBS system by completing a scenario. When you
      open the simulation, you will be provided with instructions to properly execute the
      transaction.
    </p>
    <p><span class="font-bold">Role</span>: Site Invoice Processor, Invoice Processor</p>
    <p><span class="font-bold">Scenario</span>: Create Misc Pay Invoice</p>
    <p><span class="font-bold">Transaction Code</span>: FB60</p>
    <p><span class="font-bold">Click</span> the icon on the right to begin.</p>
    <template #column_2>
      <a
        href="https://ssilrc.army.mil/resources/FMS/GFEBS/SpendingChain/6AccountsPayable/html/02_AP_FB60MiscPayInvoice_Sim/index.html"
        target="_blank"
        ><img :src="chart" class="slideImg mx-auto"
      /></a>
    </template>
  </SlideColumns>
</template>
