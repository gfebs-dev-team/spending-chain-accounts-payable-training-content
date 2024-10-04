<script setup>
import { SlideTerms } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/demonstration.svg'

const slideData = {
  title: 'Payment Roles',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 28)
})
</script>

<template>
  <SlideTerms v-bind="slideData" :termsNum="4">
    <template #main-text>
      <p>
        The Payments process requires coordination of the Payment Processor, Payment Certifier, and
        Payment interface Processing Monitor. For ARNG the 105 ARNG Movement Type Goods Acceptance
        Processor will certify the payments. The t-code used to the process is F110.
      </p>
      <p>
        <span class="font-bold">Click</span> the buttons below to learn more about the
        responsibilities for each role involved in the Payment Program process.
      </p>
    </template>
    <template #termButton_1>Payment Processor</template>
    <template #termButton_2>Payment Certifier</template>
    <template #termButton_3>Payment Interface Processing Monitor</template>
    <template #termButton_4>105 Army National Guard (ARNG)</template>

    <template #termDef_1>
      The Payment Processor sets the parameters (such as the date range) for payments to be placed
      within the Payment Proposal file.
    </template>
    <template #termDef_2>
      <ul class="list-disc pl-8 flex flex-col gap-2">
        <li>
          Verifies the Payment Proposal prepared by the Payment Processor and determines if any
          corrections are necessary
        </li>
        <li>Certifies the payment and performs Payment Run</li>
        <li>
          Is the final authority and ultimately processes all payments set up by the Payment
          Processor
        </li>
        <li>
          Re-routes the Payment Proposal back to the appropriate party for correction, if errors
          exist
        </li>
        <li>
          Allows the payments to be paid, or "blocks" the transactions from being paid with a manual
          payment block
        </li>
        <li>Can remove payment blocks from vendor invoices when justified to do so</li>
      </ul>
    </template>
    <template #termDef_3>
      <ul class="list-disc pl-8 flex flex-col gap-2">
        <li>Is responsible for monitoring inbound and outbound payment interfaces</li>
        <li>
          Routes information to and from the Payment Processor and Payment Certifier to resolve any
          errors
        </li>
      </ul>
    </template>
    <template #termDef_4>
      <p class="italic text-sm mb-4">Movement Type Goods Acceptance Processor</p>
      <ul class="list-disc pl-8 flex flex-col gap-2">
        <li>Is used only for ARNG</li>
        <li>
          The role will certify the invoice and designate it as ready for payment by manually
          creating a 105 Movement Type Goods Acceptance
        </li>
        <li>
          Allows the payments to be paid, or "blocks" the transactions from being paid with a manual
          payment block utilizing the Payment Warehouse
        </li>
        <li>
          Can remove payment blocks from vendor invoices when justified to do so using the Payment
          Warehouse
        </li>
      </ul>
    </template>
  </SlideTerms>
</template>
