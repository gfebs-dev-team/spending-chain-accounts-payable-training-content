<script setup>
import { SlideBase } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount, ref } from 'vue'
import ppa from '@/assets/s06/ppa.svg'
import nonPPA from '@/assets/s06/non-ppa.svg'

const slideData = {
  title: 'Posting Misc. Payment Invoices (2 of 2)',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides
const active = ref(-1)

onBeforeMount(() => {
  addSlide(slideData, 12)
})
</script>

<template>
  <SlideBase v-bind="slideData" :classNames="{ main: 'items-center' }">
    <template #main>
      <p class="w-full">
        <span class="font-bold">Click</span> on each button for requirements for Miscellaneous
        Payment Invoices.
      </p>

      <div class="grid grid-cols-2 grid-rows-2 h-full gap-6 p-6 justify-items-center w-4/5">
        <img
          :src="ppa"
          alt="PPA"
          class="h-full"
          @click="active = 0"
          :class="active == 0 ? 'drop-shadow-md drop-shadow-masblue' : ''"
        />
        <img
          :src="nonPPA"
          alt="Non-PPA"
          class="h-full"
          @click="active = 1"
          :class="active == 1 ? 'drop-shadow-md drop-shadow-masblue' : ''"
        />
        <div v-if="active > -1" class="bg-spacecadet mx-4 col-span-2 h-full w-full">
          <div v-if="active == 0" class="flex flex-col gap-3 p-4">
            <p class="font-bold">Misc Pays NOT subject to Prompt Payment require:</p>
            <p>
              Funds Commitment (FMZ) simultaneous commitment / obligation of funds FB60 = Invoice
            </p>
            <p>
              The FMZ Doc Type is F9 Miscellaneous Obligation Document type. The invoice document
              type is "MP Misc. Pay FM".
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
      </div>
    </template>
  </SlideBase>
</template>

<style lang="postcss" scoped>
.drop-shadow-md {
  --tw-drop-shadow: drop-shadow(0 0 6px rgb(0 0 0 / 0.04));
  --tw-drop-shadow-colored: drop-shadow(0 0 6px var(--tw-drop-shadow-color));
  filter: var(--tw-blur) var(--tw-brightness) var(--tw-contrast) var(--tw-grayscale)
    var(--tw-hue-rotate) var(--tw-invert) var(--tw-saturate) var(--tw-sepia) var(--tw-drop-shadow);
}

.drop-shadow-masblue {
  --tw-drop-shadow-color: #bbbbbb;
  --tw-drop-shadow: var(--tw-drop-shadow-colored);
}
</style>
