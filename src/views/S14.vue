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
      <a
        href="https://ssilrc.army.mil/resources/FMS/GFEBS/SpendingChain/6AccountsPayable/html/02_AP_FB60MiscPayInvoice_Demo/index.html"
        target="_blank"
        ><img :src="chart" class="slideImg mx-auto"
      /></a>
    </template>
  </SlideColumns>
</template>
