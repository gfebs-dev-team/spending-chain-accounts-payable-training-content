<script setup>
import { onBeforeMount } from 'vue'
import { useSlidesStore } from '@/stores/slides'
import { SlideTerms } from '@/components/Slide'

const slideData = {
  title: 'Contractual Invoices',
  type: 'content',
  section: 'Invoice Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 6)
})
</script>

<template>
  <SlideTerms v-bind="slideData" :termsNum="2">
    <template #main-text>
      <p>
        There are two key steps you should understand in the processing of contractual invoices:
        Invoice Entry and Matching.
      </p>
      <p>
        Once Invoices are entered into GFEBS, they go through the matching process (i.e. three or
        four way) before they are paid. A three way match compare the Invoice, Purchase Order (PO)
        and Goods Receipt (GR). A four way math compares the Invoice, PO, GR and Goods Acceptance
        document.
      </p>
      <p>
        <span class="font-bold">Click</span> the Invoice Entry and the Matching buttons to learn
        more about each step.
      </p>
    </template>

    <template #termButton_1>Invoice Entry</template>
    <template #termDef_1>
      <ul class="list-disc pl-4">
        <li>
          The Army can receive an invoice from a vendor in a number of ways. A contractual invoice
          is interfaced into GFEBS through WAWF. For exceptions that need to be entered manually,
          the MIRO transaction is used.
        </li>
        <li>An invoice is blocked for payment if it is posted prior to GR / acceptance.</li>
        <li>
          For payments that are disbursed by DDS, which is the disbursing system that processes
          payments for vendors Outside Continental United States (OCONUS), the invoice will contain
          a Payment Method Supplement (PMS) field specific to DDS. The PMS field represents the
          DSSN.
        </li>
      </ul>
    </template>

    <template #termButton_2>Matching</template>
    <template #termDef_2>
      <ul class="list-disc pl-4">
        <li>
          The invoice is matched against other documentation that might exist from the Procurement
          process including the GR, goods acceptance document and the PO.
        </li>
        <li>
          For the ARNG, the invoice matching is completed after the 105 ARNG Movement Type Goods
          Acceptance Processor has manually enters tie goods acceptance. The invoice is unblocked
          and ready for payment. The four-way match is completed when an invoice, PO, GR and a goods
          acceptance document and invoice exist in GFEBS.
        </li>
        <li>
          The invoice cannot be greater than the amount obligated on the contract or the amount on
          the goods receipt (either dollars or quantity) or it is blocked.
        </li>
      </ul>
    </template>
  </SlideTerms>
</template>
