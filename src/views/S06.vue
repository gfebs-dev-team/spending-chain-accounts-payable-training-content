<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount, ref } from 'vue'
import target from '@/assets/img/target.svg'

const slideData = {
  title: 'Groups of Invoices',
  type: 'content',
  section: 'Invoicing Process'
}

const slides = useSlidesStore()
const { addSlide } = slides
const active = ref(-1)

onBeforeMount(() => {
  addSlide(slideData, 5)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <p>GFEBS has two main groups of invoices:</p>
    <ol>
      <li>Invoices subject to Prompt Payment Act (PPA).</li>
      <li>Invoices NOT subject to the Prompt Payment Act (Non PPA).</li>
    </ol>
    <p>
      <span class="font-bold">Click</span> on each button below to learn more about these two
      groups.
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
    <template #column_2>
      <div v-if="active > -1" class="bg-spacecadet mx-4">
        <div v-if="active == 0" class="flex flex-col gap-3 p-4">
          <p class="font-bold">PPA Key Points:</p>
          <ul class="list-disc pl-4">
            <li>
              Invoices subject to the Prompt Payment Act (PPA) reference a purchase order (PO) and a
              goods receipt (GR) / acceptance. They may relate to a Standard Procurement System
              (SPS) PO, which results in a contract with a vendor, or a miscellaneous pay PO that is
              subject to PPA.
            </li>
            <li>
              If the invoice is related to an SPS PO, it is inter-faced into GFEBS through the Wide
              Area Work Flow (WAWF), which is addressed in a separate course.
            </li>
            <li>
              If the invoice relates toa MISC Pay PO, supporting documentation must be attached to
              the invoice as supporting documentation. Interest will accrue according to the terms
              on the PO.
            </li>
          </ul>
        </div>
        <div v-if="active == 1" class="flex flex-col gap-3 p-4">
          <p class="font-bold">Non-PPA Key Points:</p>
          <ul class="list-disc pl-4">
            <li>
              Invoices not subject to PPA reference a funds commitment document created in GFEBS
              using the FMZI transaction and do not reference POs or GRs.
            </li>
            <li>
              Miscellaneous payment invoices not subject to PPA are entered using the transaction
              FB60 at the installation by the Site Invoice Processor.
            </li>
            <li>
              Examples of miscellaneous payment invoices not subject to PPA include: Apprehension
              Reimbursements and Confinement Costs, Attorney's Fees and Demurrage Fees.
            </li>
          </ul>
        </div>
      </div>
    </template>
  </SlideColumns>
</template>

<style lang="postcss" scoped>
.drop-shadow-md {
  --tw-drop-shadow: drop-shadow(0 0 5px rgb(0 0 0 / 0.04));
  --tw-drop-shadow-colored: drop-shadow(0 0 5px var(--tw-drop-shadow-color));
  filter: var(--tw-blur) var(--tw-brightness) var(--tw-contrast) var(--tw-grayscale)
    var(--tw-hue-rotate) var(--tw-invert) var(--tw-saturate) var(--tw-sepia) var(--tw-drop-shadow);
}

.drop-shadow-masblue {
  --tw-drop-shadow-color: #3a4b6f;
  --tw-drop-shadow: var(--tw-drop-shadow-colored);
}
</style>
