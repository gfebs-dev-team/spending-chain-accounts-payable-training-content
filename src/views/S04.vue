<script setup>
import { onBeforeMount } from 'vue'
import { useSlidesStore } from '@/stores/slides'
import { SlideTerms } from '@/components/Slide'
import invoiceProcessor from '@/assets/accounts3.svg'

const slideData = {
  title: 'Invoicing Roles in GFEBS',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 3)
})
</script>

<template>
  <SlideTerms v-bind="slideData" :termsNum="3" :reverse="true">
    <template #main-text>
      <p class="font-bold">The roles involved in the Invoicing Process section are:</p>
      <ul class="list-disc flex flex-col pl-12 gap-3">
        <li>Site Invoice Processor</li>
        <li>Invoice Processor</li>
        <li>Invoice Interface Processing Monitor</li>
      </ul>
      <p>
        <span class="font-bold">Click</span> on each role to learn more about the responsibilities
        for each role involved in the Invoicing Activity
      </p>
    </template>
    <img :src="invoiceProcessor" alt="Invoice Processor" class="h-2/5 px-4 mx-auto" />
    <template #termButton_1>Site Invoice Processor</template>
    <template #termDef_1>
      The <span class="font-bold">Site Invoice Processor</span> receives, verifies and creates
      manual non-contractual miscellaneous payment invoices in GFEBS at the installation. This
      ensures that miscellaneous payment invoices that are not subject to Prompt Payment Act are
      accurate and meet requirements. Furthermore, the Site Invoice Processor can release
      non-contractual invoices that are blocked for payment.
    </template>

    <template #termButton_2>Invoice Processor</template>
    <template #termDef_2>
      The <span class="font-bold">Invoice Processor</span> receives, verifies and records
      contractual miscellaneous payment invoices in GFEBS at DFAS. This ensures all supporting
      information or documentation is legal, proper, complete and correct. In addition, the Invoice
      Processor can release invoices that are blocked for payment and may coordinate with the
      Invoice Interface Processing Monitor to help resolve interface errors.
    </template>

    <template #termButton_3>Invoice Interface Processing Monitor</template>
    <template #termDef_3>
      The <span class="font-bold">Invoice Interface Processing Monitor</span>
      monitors the interfacing of invoices from WAWF and AXOL. The Invoice Interface Processing
      Monitor identifies and resolves any interface errors. In addition, the Invoice Processor
      releases invoices that are blocked and may coordinate with the Invoice Processor.
    </template>
  </SlideTerms>
</template>
