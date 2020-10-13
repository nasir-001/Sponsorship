<template>
  <div>
      <div class="min-h-screen">
        <div class="absolute top-0 left-0">
            <div class="flex opacity-50 p-4">
                <svg class="h-6 w-6 mr-2 text-gray-700 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><path d="M496.616 372.639l70.012-70.012c16.899-16.9 9.942-45.771-12.836-53.092L512 236.102V96c0-17.673-14.327-32-32-32h-64V24c0-13.255-10.745-24-24-24H248c-13.255 0-24 10.745-24 24v40h-64c-17.673 0-32 14.327-32 32v140.102l-41.792 13.433c-22.753 7.313-29.754 36.173-12.836 53.092l70.012 70.012C125.828 416.287 85.587 448 24 448c-13.255 0-24 10.745-24 24v16c0 13.255 10.745 24 24 24 61.023 0 107.499-20.61 143.258-59.396C181.677 487.432 216.021 512 256 512h128c39.979 0 74.323-24.568 88.742-59.396C508.495 491.384 554.968 512 616 512c13.255 0 24-10.745 24-24v-16c0-13.255-10.745-24-24-24-60.817 0-101.542-31.001-119.384-75.361zM192 128h256v87.531l-118.208-37.995a31.995 31.995 0 0 0-19.584 0L192 215.531V128z"/></svg>
                <span class="text-gray-700">SponsorShip</span>
            </div>
        </div>
        <div class="max-w-xl px-6 mx-auto pt-16 pb-24">
            <h1 class="text-3xl text-center mb-8">Which episodes would you like to sponsor?</h1>
            <ul>
                <li v-bind:key="sponsorableSlot.id" v-for="sponsorableSlot in sponsorableSlots" class="mb-4">
                    <sponsorable-slot :sponsorable-slot="sponsorableSlot"
                    :selected="selectedSlots.includes(sponsorableSlot.id)"
                    @input="handleSponsorableSlotInput(sponsorableSlot, $event)"
                    >
                    </sponsorable-slot>
                </li>
            </ul>
        </div>
        <div class="bg-white border-t-2 border-gray-300 fixed bottom-0 inset-x-0">
            <div class="max-w-xl mx-auto py-4 px-6">
                <div class="flex justify-between items-center">
                    <div class="sm:w-3/4 sm:flex sm:justify-between sm:items-center">
                        <div class="text-base sm:text-lg">1 episode selected</div>
                        <div class="sm:text-right">
                            <span class="sm:block text-lg font-bold">$500</span>
                            <span class="sm:block text-sm text-gray-700">USD</span>
                        </div>       
                    </div>
                    <div class="sm:w-1/4 flex justify-end items-center">
                        <pay-button>Pay now</pay-button>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import SponsorableSlot from './SponsorableSlot'
import PayButton from './PayButton'

export default {
    components: {
        SponsorableSlot,
        PayButton,
    },
    data() {
        return {
            selectedSlots: [2, 3],
            sponsorableSlots: [
                {
                    id: 1,
                    title: 'Full Stack Raduio: Episode 89',
                    publish_date: '2018-06-05',
                    price: 500,
                    image_url: '/img/index.jpg',
                },
                {
                    id: 2,
                    title: 'Full Stack Raduio: Episode 90',
                    publish_date: '2018-06-20',
                    price: 400,
                    image_url: '/img/index.jpg',
                },
                {
                    id: 3,
                    title: 'Full Stack Raduio: Episode 91',
                    publish_date: '2018-06-25',
                    price: 550,
                    image_url: '/img/index.jpg',
                },
                {
                    id: 4,
                    title: 'Full Stack Raduio: Episode 92',
                    publish_date: '2018-06-27',
                    price: 570,
                    image_url: '/img/index.jpg',
                },
            ],
        }
    },
    methods: {
        handleSponsorableSlotInput(sponsorableSlot, newValue) {
            console.log('blah')
            if (newValue) {
                this.selectedSlots = [...this.selectedSlots, sponsorableSlot.id]
            }
            else {
                this.selectedSlots = this.filter(this.selectedSlots, (slot) => slot.id !== sponsorableSlot.id)
            }
        }
    }
}
</script>

<style>

</style>