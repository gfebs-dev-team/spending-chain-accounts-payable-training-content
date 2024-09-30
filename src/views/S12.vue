<script setup>
import { SlideBase } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount, ref } from 'vue'
import target from '@/assets/img/target.svg'

const slideData = {
  title: 'Posting Misc. Payment Invoices (2 of 2)',
  type: 'content',
  section: 'Invoice Process'
}

const slides = useSlidesStore()
const { addSlide } = slides
const active = ref(-1)

onBeforeMount(() => {
  addSlide(slideData, 11)
})
</script>

<template>
  <SlideBase v-bind="slideData" :classNames="{ main: '' }">
    <template #main>
      <p>
        <span class="font-bold">Click</span> on each button for requirements for Miscellaneous
        Payment Invoices.
      </p>
      <div class="grid grid-cols-2 gap-3 mt-6">
        <img
          :src="target"
          alt="PPA"
          @click="active = 0"
          :class="active == 0 ? 'drop-shadow-md drop-shadow-masblue' : ''"
        />
        <img
          :src="target"
          alt="Non-PPA"
          @click="active = 1"
          :class="active == 1 ? 'drop-shadow-md drop-shadow-masblue' : ''"
        />
      </div>
      <div v-if="active > -1" class="bg-spacecadet mx-4">
        <div v-if="active == 0" class="flex flex-col gap-3 p-4">
          <p class="font-bold">Misc Pays NOT subject to Prompt Payment require:</p>
          <p>Funds Commitment (FMZ) simultaneous commitment / obligation of funds FB60 = Invoice</p>
          <p>
            The FMZ Doc Type is F9 Miscellaneous Obligation Document type. The invoice document type
            is "MP Misc. Pay FM".
          </p>
        </div>
        <div v-if="active == 1" class="flex flex-col gap-3 p-4">
          <p class="font-bold">
            Miscellaneous Payments subject to the Prompt Payment require the following:
          </p>
          <p>Misc Pay PR = Commitment of funds</p>
          <p>Misc Pay PO = Obligation of Funds</p>
          <p>MIGO = Goods Receipt I acceptance</p>
          <p>MIRO = Invoice</p>
        </div>
      </div>
    </template>
  </SlideBase>
</template>
