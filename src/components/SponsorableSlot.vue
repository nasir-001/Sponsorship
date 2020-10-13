<template>
  <div>
      <div @click="emit('input', !selected)" class="bg-white justify-between rounded-lg shadow py-4 flex group border-2 border-transparent cursor-pointer select-none hover:border-indigo-400">
        <div class="sm:w-3/4 flex items-center pl-4">
            <img class="block h-16 w-16 mr-4 rounded" :src="sponsorableSlot.image_url" alt="">
            <div class="flex-1 overflow-x-hidden sm:flex sm:justify-between">
                <div class="mb-1 sm:mb-0">
                    <div class="text-base sm:text-lg font-bold truncate">{{ sponsorableSlot.title }}</div>
                    <div class="text-xs sm:text-sm text-gray-700">june 6, 2018</div>
                </div>
                <div class="sm:text-right">
                    <span class="sm:block text-lg font-bold">${{ sponsorableSlot.price }}</span>
                    <span class="sm:block text-sm text-gray-700">USD</span>
                </div>
            </div>
        </div>
        <div class="sm:w-1/4 flex justify-end items-center pr-4">
            <svg v-if="selected" class="h-6 w-6 text-green-500 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M256 8C119.033 8 8 119.033 8 256s111.033 248 248 248 248-111.033 248-248S392.967 8 256 8zm0 48c110.532 0 200 89.451 200 200 0 110.532-89.451 200-200 200-110.532 0-200-89.451-200-200 0-110.532 89.451-200 200-200m140.204 130.267l-22.536-22.718c-4.667-4.705-12.265-4.736-16.97-.068L215.346 303.697l-59.792-60.277c-4.667-4.705-12.265-4.736-16.97-.069l-22.719 22.536c-4.705 4.667-4.736 12.265-.068 16.971l90.781 91.516c4.667 4.705 12.265 4.736 16.97.068l172.589-171.204c4.704-4.668 4.734-12.266.067-16.971z"/></svg>
            <svg v-if="!selected" class="block hover:hidden h-6 w-6 text-gray-500 fill-current" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M11.5 0c6.347 0 11.5 5.153 11.5 11.5s-5.153 11.5-11.5 11.5-11.5-5.153-11.5-11.5 5.153-11.5 11.5-11.5zm0 1c5.795 0 10.5 4.705 10.5 10.5s-4.705 10.5-10.5 10.5-10.5-4.705-10.5-10.5 4.705-10.5 10.5-10.5zm.5 10h6v1h-6v6h-1v-6h-6v-1h6v-6h1v6z"/></svg>
            <svg v-if="!selected" class="hidden hover:block h-6 w-6 text-indigo-500 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M352 240v32c0 6.6-5.4 12-12 12h-88v88c0 6.6-5.4 12-12 12h-32c-6.6 0-12-5.4-12-12v-88h-88c-6.6 0-12-5.4-12-12v-32c0-6.6 5.4-12 12-12h88v-88c0-6.6 5.4-12 12-12h32c6.6 0 12 5.4 12 12v88h88c6.6 0 12 5.4 12 12zm96-160v352c0 26.5-21.5 48-48 48H48c-26.5 0-48-21.5-48-48V80c0-26.5 21.5-48 48-48h352c26.5 0 48 21.5 48 48zm-48 346V86c0-3.3-2.7-6-6-6H54c-3.3 0-6 2.7-6 6v340c0 3.3 2.7 6 6 6h340c3.3 0 6-2.7 6-6z"/></svg>
        </div>
    </div>
  </div>
</template>

<script>

export default {
    props: ['sponsorableSlot', 'selected'],
    methods: {

    }
}
</script>

<style>

</style>