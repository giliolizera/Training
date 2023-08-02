<template>
  <Upside />
  <div class="bg-slate-700">
    <div class="w-full px-4 pt-16">
      <div class="mx-auto w-full max-w-md rounded-2xl bg-gray-100 p-2">
        <button 
        @click="exibir = !exibir" type="button"
        class="flex w-full justify-between rounded-lg bg-purple-100 px-4 py-2 text-left text-sm font-medium text-slate-900 hover:bg-purple-200 focus:outline-none">
          What is your refund policy?
        </button>
        <transition 
          enter-active-class="transition duration-700 ease-out" 
          enter-from-class="opacity-0"
          enter-to-class="opacity-100" 
          leave-active-class="transition duration-500 ease-in" 
          leave-from-class="opacity-100"
          leave-to-class="opacity-0">
          <div v-if="exibir" class="px-4 pb-2 pt-4 text-sm text-gray-900">If you're unhappy with your purchase for any
            reason, email us within 90 days and we'll refund you in full, no questions asked.</div>
        </transition>
        <div class="mt-2">
          <button @click="exibir2 = !exibir2"
            class="flex w-full justify-between rounded-lg bg-purple-100 px-4 py-2 text-left text-sm font-medium text-slate-900 hover:bg-purple-200 focus:outline-none">
            Do you offer technical support?
          </button>
          <transition 
          enter-active-class="transition duration-500 ease-out" 
          enter-from-class="opacity-0"
          enter-to-class="opacity-100" 
          leave-active-class="transition duration-500 ease-in" 
          leave-from-class="opacity-100"
          leave-to-class="opacity-0">
            <div v-if="exibir2" class="px-4 pb-2 pt-4 text-sm text-gray-900">No.</div>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Upside from './Upside.vue'

export default {
  data: () => ({
    exibir: true,
    exibir2: true,
  }),
  components: {
    Upside
  },
}
</script>
