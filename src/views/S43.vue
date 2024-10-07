<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/img/accounts15.svg'

const slideData = {
  title: 'Review',
  type: 'content',
  section: 'Lesson Review'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 42)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>
      This concludes the Accounts Payable Process lesson. The overview consisted of an Introduction
      to Invoicing and the Payment Program.
    </p>

    <p>
      In the invoicing section, we reviewed the types of Invoices used as well as Invoicing in
      GFEBS. These included:
    </p>

    <ul class="pl-8 list-disc">
      <li>Contractual Invoices</li>
      <li>Miscellaneous Payment Invoices</li>
      <li>Management of Blocked invoices</li>
    </ul>

    <p>
      We also discussed the GFEBS Payment Program Process which includes the Payment Interfaces,
      Process Flow and key roles.
    </p>

    <p>
      You may exit the lesson by clicking the Exit button below or use the navigation buttons (also
      below) to review the lesson's content.
    </p>
    <template #column_2>
      <img :src="chart" className="p-12" />
    </template>
  </SlideColumns>
</template>
