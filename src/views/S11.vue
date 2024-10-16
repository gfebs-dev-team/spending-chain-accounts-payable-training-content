<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/accounts9.svg'

const slideData = {
  title: 'Miscellaneous Payment Invoices',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 10)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      As previously mentioned invoices for non-contractual goods / services are identified as
      miscellaneous payment invoices. These invoices are manually entered by the Site Invoice
      Processor.
    </p>
    <p>
      Invoices for miscellaneous payments that are subject to PPA are similar to contractual
      invoices in that they are based on an invoice from a vendor and use the MIRO transaction code.
      The Misc Pay Invoice is identified as such by using a different document type ARM" which
      identifies it as a Misc Pay PO. The invoice type can be selected from the Details Tab in the
      Invoice in the field labeled Doc. Type.
    </p>
    <p>
      Invoices for miscellaneous payments not subject to PPA must also have all supporting
      documentation. These payment can be for reimbursements of tuition and / or certifications. The
      T-code used for this type of miscellaneous payment is FB60. The document type "MP" designated
      this invoice as a miscellaneous payment invoice.
    </p>
    <p>
      Miscellaneous payments can be made via check or EFT. The payment method is derived from the
      Vendor's Master Data.
    </p>
    <template #column_2>
      <img :src="chart" className="self-start px-16" />
    </template>
  </SlideColumns>
</template>
