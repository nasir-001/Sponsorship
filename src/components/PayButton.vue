<template>
  <button @click="modalOpen = true" class="rounded-md px-4 py-2 text-lg font-medium leading-normal text-white bg-indigo-700 hover:bg-indigo-500">
        <slot></slot>
        <complete-purchase-modal :open="modalOpen" @close="modalOpen = false"></complete-purchase-modal>
  </button>
</template>

<script>
import CompletePurchaseModal from './CompletePurchaseModal'

export default {
    components: {
        CompletePurchaseModal
    },
data() {
    return {
      modalOpen: false,
    }
  },
}
</script>

<style>

</style>