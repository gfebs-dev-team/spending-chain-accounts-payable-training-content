<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/accounts16.svg'

const slideData = {
  title: 'Payment Process',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 29)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p class="font-bold">Below are key notes regarding the Payment Process:</p>
    <p>
      Pending payment documents are scheduled in the payment queue and remain there until they are
      processed and paid.
    </p>
    <p>Payments are processed in accordance with regulatory and statutory time requirements.</p>
    <p>
      The system generates a Payment Ready file and automatically clears open items once a
      disbursement is made.
    </p>
    <p>
      Vendor accounts are updated by the system to reflect the progression of pending payment
      documents.
    </p>
    <template #column_2>
      <img :src="chart" class="slideImg" />
    </template>
  </SlideColumns>
</template>
