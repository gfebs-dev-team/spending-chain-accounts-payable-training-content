<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/demonstration.svg'

const slideData = {
  title: 'Pre-Validation',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 6)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      In cases where an invoice is paid "For Others" or "By Others" the pre-validation of the
      invoice takes place within the Accounts Payable process.
    </p>
    <p>
      Transactions By Others (TBO) and Transactions For Others (TFO) are handled using the Account
      Pre-Validation Module (APVM) and the Pay Pre-Validation Module (PPVM).
    </p>
    <template #column_2>
      <a href=""><img :src="chart" className="h-full p-12" /></a>
    </template>
  </SlideColumns>
</template>
