<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import image from '@/assets/spendingchain.svg'

const slideData = {
  title: 'Welcome to Accounts Payable',
  type: 'content',
  section: 'Introduction'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 0)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :classNames="{ main: 'gap-4' }" :columns="1">
    <p>
      Welcome to the Accounts Payable lesson. The Accounts Payable Process encompasses Invoicing and
      the Payment Process.
    </p>
    <p>The topics that will be presented are as follows:</p>
    <ul class="list-disc pl-4">
      <li>Roles involved in the Accounts Payable Process</li>
      <li>Types of Invoices</li>
      <li>How to manage invoices</li>
      <li>Steps involved in the payment process</li>
    </ul>
    <p>We will start by learning about Invoicing and the roles required in the process.</p>
    <template #column_2>
      <img :src="image" class="h-3/4 md:p-8 md:pt-0 object-contain" />
    </template>
  </SlideColumns>
</template>
