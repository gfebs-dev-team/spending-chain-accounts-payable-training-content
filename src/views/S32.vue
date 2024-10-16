<script setup>
import { SlideColumns } from '@/components/Slide'
import AppButton from '@/components/AppButton.vue'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/demonstration.svg'

const slideData = {
  title: 'Treasury Payment',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 31)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      GFEBS currently has several vendors which are paid directly by Treasury. When an invoice with
      Payment Method Supplement (PMS) 02 becomes free to pay, the Accounts Payable GFEBS
      certification team will review the invoice for validity. Once validated the team certifies the
      payment run which generates and sends the file to Treasury for disbursement. Treasury
      disburses through the Federal Reserve Bank (FRB) to the vendor's bank. Treasury provides the
      clearing information including the Electronic Funds Transfer (EFT) trace number that is posted
      in GFEBS as the entitlement system of record.
    </p>
    <p>
      All accounting documents in GFEBS (commitment, obligation, acceptance, invoice, payment and
      disbursement) are linked and available to view for payment history.
    </p>
    <p>
      <span class="font-bold">Click</span> the button for the supporting document that shows the
      step by step process on researching these payments.
    </p>
    <template #column_2>
      <img :src="chart" className="p-12" />
      <AppButton class="h-min">Support Document</AppButton>
    </template>
  </SlideColumns>
</template>
<!--TODO: Add file opener component & get file-->
