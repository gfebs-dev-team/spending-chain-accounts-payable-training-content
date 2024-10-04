<script setup>
import { SlideColumns } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount, ref } from 'vue'
import chart from '@/assets/img/demonstration.svg'

const slideData = {
  title: 'GFEBS Payment Interfaces',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides
const active = ref(-1)

onBeforeMount(() => {
  addSlide(slideData, 30)
})
</script>

<template>
  <SlideColumns v-bind="slideData" :columns="1">
    <template #column_2>
      <p><span class="font-bold">Click</span> on each bullet in the graphic to learn more.</p>
      <div v-if="active > -1" class="bg-spacecadet mx-4">
        <div v-if="active == 0" class="flex flex-col gap-3 p-4">
          <h2 class="font-bold">International Treasury Service (ITS)</h2>
          <p>
            GFEBS includes functionality that manages currency, exchange rates and revaluation.
            Exchange rates are required to translate transactions in foreign currencies to and from
            U.S. dollars. The exchange rates are provided daily (business days only) by the Treasury
            Departments International Treasury Services (ITS) in a Post Pay file.
          </p>
        </div>
        <div v-if="active == 1" class="flex flex-col gap-3 p-4">
          <h2 class="font-bold">Deployable Disbursing System (DDS)</h2>
          <p>
            is a system that processes disbursements as part of the SDI. DDS will process payments
            for vendors Outside Continental United States (OCONUS). The PMS field on the invoice
            determines if ADS or DDS should be used to perform the disbursement. If the value in the
            PMS field is not equal to "00" then DDS is used.
          </p>
        </div>
        <div v-if="active == 2" class="flex flex-col gap-3 p-4">
          <h2 class="font-bold">Automated Disbursing System (ADS)</h2>
          <p>
            is a system that DFAS uses to process disbursements as part Of the SDI. ADS processes
            payments for vendors in the Continental United States (COWS). The PMS field on the
            invoice determines if ADS or DDS must be used t perform the disbursement. If the value
            in the PMS field is equal to "00" then ADS is used.
          </p>
        </div>
        <div v-if="active == 3" class="flex flex-col gap-3 p-4">
          <h2 class="font-bold">Defense Finance and Accounting Services</h2>
          <p>
            (DFAS)/Defense Cash Accountability System (DCAS) DCAS is the system selected by DFAS to
            be the single cash accountability system for the DOD. Cash accountability includes the
            reporting of disbursements, reimbursements, deposits and receipts to the U.S. Treasury.
            For the Payment process, the focus of this interface specifically is on the sending of
            SF 1081 transactions to DCAS.
          </p>
        </div>
      </div>
    </template>
  </SlideColumns>
</template>
<!-- TODO: Needs Graphic -->
