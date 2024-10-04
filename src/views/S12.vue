<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/accounts10.svg'

const slideData = {
  title: 'Posting Misc. Payment Invoices (1 of 2)',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 11)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      The Site Invoice Processor should not process a Misc. Payment Invoice without supporting
      documentation.
    </p>
    <p>
      After creating the invoice, they must attach supporting documentation via FB02. This is true
      regardless of the invoice type that was entered, whether it was an MIRO invoice for Misc Pay
      subject to PPA or an FB60 for Misc Pay not subject to PPA. Only after the supporting
      documentation is attached will the invoice route for approval.
    </p>
    <p>
      It is of upmost importance that the correct document types are used to reflect a miscellaneous
      payment. Using the wrong document type in any of the documents required will cause an issue
      with routing.
    </p>
    <p>
      Once supporting documentation is attached, the Misc. Pay Approver receives a notification
      advising of their pending tasks. Upon review and approval, the Miscellaneous Payment will
      route to DFAS for Payment Processing.
    </p>
    <template #column_2>
      <img :src="chart" className="self-start px-4" />
    </template>
  </SlideColumns>
</template>
