<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '../stores/slides'
import { onBeforeMount } from 'vue'

const slideData = {
  title: 'SlideColumns',
  type: 'content',
  section: 'Section 1: Slide Types'
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
    <template #column_2></template>
  </SlideColumns>
</template>

<style scoped lang="scss">
code {
  background-color: #1a1818;
  word-wrap: break-word;
  box-decoration-break: clone;
  padding: 0.1rem 0.3rem 0.2rem;
  border-radius: 0.2rem;
  font-family: Consolas, Monaco, 'Lucida Sans', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
