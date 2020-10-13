<template>
  <div>
    <portal to="modals">
        <div v-show="open" class="fixed inset-0 bg-black-20 flex justify-center items-center p-6">
            <div ref="modal" @focusout="handleFocusOut" class="max-w-md shadow-2xl w-full bg-white py-6 px-10 rounded-lg">
                <h2 class="text-xl mb-2 font-semibold text-black text-center">Complete your purchase</h2>
                <form action="#" method="POST">
                    <label class="block mb-4">
                        <span class="block mb-2 text-sm font-bold">Company</span>
                        <input ref="companyInput" class="block border border-gray-400 bg-gray-200 leading-tight rounded px-4 py-2 w-full text-black" placeholder="DigiTechnoSoft Inc.">
                    </label>
                    <label class="block mb-4">
                        <span class="block mb-2 text-sm font-bold">Email</span>
                        <input class="block border border-gray-400 bg-gray-200 leading-tight rounded px-4 py-2 w-full text-black" placeholder="your-name@your-company.com">
                    </label>
                    <label class="block mb-6">
                        <span class="block mb-2 text-sm font-bold">Credit Card</span>
                        <input class="block border border-gray-400 bg-gray-200 leading-tight rounded px-4 py-2 w-full text-black" placeholder="Your Card.">
                    </label>
                    <div>
                        <button type="button" class="mb-4 block w-full rounded-md px-4 py-2 text-lg font-medium leading-normal text-white bg-indigo-700 hover:bg-indigo-500">
                            Pay $1500 now
                        </button>
                        <p class="text-gray-700 leading-normal text-center">We'll reach out for your sponsorship information after you've yout purchase.</p>
                    </div>
                </form>
            </div>
        </div>
     </portal>
  </div>
</template>

<script>
export default {
props: ['open'],
watch: {
    open(newValue) {
        if (newValue) {
            this.$nextTick(() => {
                setTimeout(() => {
                    this.$refs.companyInput.focus()
                }, 100)
            })
        }
    }
},
created() {
      const escapeListener = (e) => {
          if(e.key === 'Escape') {
              this.$emit('close')
          }
      }
      document.addEventListener('keydown', escapeListener)

      this.$on('hook:beforeDestroy', () => {
          document.removeEventListener('keydown', escapeListener)
      })
  },
  methods: {
      handleFocusOut(e) {
          if (this.$refs.modal.contains(e.relatedTarget)) {
              return
          }
          
          this.$emit('close')
      }
  }
}
</script>

<style>

</style>