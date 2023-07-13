<template>
  <div class="bg-slate-600">
  <div class="w-full px-4 pt-16">
    <div class="mx-auto w-full max-w-md rounded-2xl bg-slate-900 p-2">
      <button @click="exibir = !exibir" type="button" class="flex w-full justify-between rounded-lg bg-slate-800 px-4 py-2 text-left text-sm font-medium text-purple-300 hover:bg-slate-700 focus:outline-none">
        <span>What is your refund policy?</span>
      </button>
      <div v-if="exibir" class="px-4 pb-2 pt-4 text-sm text-gray-500">If you're unhappy with your purchase for any reason, email us within 90 days and we'll refund you in full, no questions asked.</div>
        <div class="mt-2">
          <button @click="exibir2 = !exibir2" class="flex w-full justify-between rounded-lg bg-slate-800 px-4 py-2 text-left text-sm font-medium text-purple-300 hover:bg-slate-700 focus:outline-none">
            <span>Do you offer technical support?</span>
          </button>
          <div v-if="exibir2" class="px-4 pb-2 pt-4 text-sm text-gray-500">No.</div>
        </div>
    </div>
  </div>
  </div>
  <div class="bg-slate-600 w-full h-16"></div>
</template>

<script>
export default {
  data:() => ({
    exibir: false,
    exibir2: false
  }),
  methods: {

  }
}
</script>
