<script setup>
import { SlideTerms } from '@/components/Slide'
import { useSlidesStore } from '@/stores/slides'
import { onBeforeMount } from 'vue'
import chart from '@/assets/demonstration.svg'

const slideData = {
  title: 'Payment Process Flow',
  type: 'content',
  section: 'Payment Program'
}

const slides = useSlidesStore()
const { addSlide } = slides

onBeforeMount(() => {
  addSlide(slideData, 32)
})
</script>

<template>
  <SlideTerms v-bind="slideData" :termsNum="6">
    <template #main-text>
      <p>Let's take a step-by-step look at the payment process.</p>
      <p>
        <span class="font-bold">Click</span> on each button below to follow the process in more
        detail.
      </p>
    </template>

    <template #termButton_1>Payment Proposal</template>
    <template #termDef_1>
      Invoices that are eligible and due for payment are identified during Payment Proposal. The
      Payment Proposal displays the open items that are proposed by the payment program. The open
      items are based on the payment parameters that are set before Corporate Electronic Funds
      Transfer (CEFT) Validation can occur.
    </template>

    <template #termButton_2>CEFT Validation</template>
    <template #termDef_2>
      <p>
        CEFT Validation checks EFT information for all vendors and individuals in the system with
        open items due for payment.
      </p>
      <p>
        CEFT Validation ensures that GFEBS has the most current EFT information for those vendors.
        Prior to payment, EFT information in the vendor master data records are updated via the CEFT
        interface, if changes are needed.
      </p>
      <p>
        After the CEFT Validation and updates are completed, the payment program will be processed.
      </p>
    </template>

    <template #termButton_3>Certify Payment</template>
    <template #termDef_3>
      <p>Payments are certified by the Payment Certifier to check for errors.</p>
      <p>
        For ARNG, the payments are certified after the 105 ARNG Movement Type Goods Acceptance
        Processor has manually created the 105 Movement Type Goods Acceptance. The invoice will be
        unblocked and ready for payment
      </p>
      <p>
        Payments with errors are blocked manually by the Payment Certifier, sent back to the Invoice
        Processor or the Site Invoice Processor to resubmit The Payment Warehouse transaction
        ZPMT_Warehouse is used to identify, review and block or unblock invoices.
      </p>
    </template>

    <template #termButton_4>Payment Run</template>
    <template #termDef_4>
      <p>
        Once all payments have been certified, the Payment Run is completed, which creates the
        payment transaction file.
      </p>
      <p>
        The payment program is run separately for check and EFT payments and generates multiple
        files. These files are called Ready-to- Pay files. Each payment that has been run has a
        unique Payment Run ID and payment date, which is used to capture data.
      </p>
    </template>

    <template #termButton_5>File Sent to Disbursement (ADS or DDS)</template>
    <template #termDef_5>
      <p>Ready-to-Pay files are routed to ADS or DDS for processing.</p>
      <p>
        After all the data for the outbound file has been captured for disbursements, the file must
        be formatted in the required layout and sent out to ADS or DDS for payment processing.
      </p>
    </template>

    <template #termButton_6>Confirmation Sent to GFEBS</template>
    <template #termDef_6>
      Incoming disbursement records from ADS or DDS are matched up to existing "disbursement in
      transit" records in GFEBS by using specific information recorded on the outbound Ready- to-Pay
      file. The same information comes back on the inbound Post Pay file with the addition of check
      or EFT trace number indicating payments were made. The disbursement is then posted in GFEBS.
    </template>
  </SlideTerms>
</template>
