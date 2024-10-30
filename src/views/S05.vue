<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import target from '@/assets/accounts4.svg'

const slideData = {
  title: 'Types of Invoices',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 4)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1" :classNames="{ 2: 'self-start' }">
    <p>
      GFEBS provides us two transaction codes for entering invoices, FB60 and MIRO. Some of these
      invoices interface via a system partner, Wide Area Work Flow (WAWF), while others are manually
      entered by DFAS and/or the activity based on the function being performed.
    </p>
    <p>
      <span class="font-bold">Misc Pay invoices</span> are created locally by the Site Invoice
      Processor
    </p>
    <p>
      <span class="font-bold">Contractual Invoices</span> are posted via interface with WAWF. If
      failures occur they are identified by the Invoice Interface Processor and resolved by the
      Invoice Processor at DFAS.
    </p>
    <template #column_2>
      <img :src="target" alt="target" class="h-3/4 md:p-8 md:pt-0 object-contain" />
    </template>
  </SlideColumns>
</template>
