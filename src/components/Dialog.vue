<template>
   <div class="bg-green-400">
      <div class="mx-auto pt-16 w-32 max-w-md rounded-md">
         <button v-if="show" @click="exibir = true, show = false" class="rounded-md bg-black bg-opacity-20 px-4 py-2 text-sm font-medium text-white hover:bg-opacity-30">
            Open Dialog
         </button>
      </div>
      <div v-if="exibir" class="mx-auto max-w-md rounded-md bg-white p-4 space-y-2">
         <p class="pl-1 font-medium">Payment Successful</p>
         <p class="pl-1 text-sm text-gray-500">Your payment has been successfully submitted. We`ve sent you an email with all of the details of your order.</p>
         <button @click="exibir = false, show = true" class="inline-flex justify-center rounded-md border border-transparent bg-blue-200 px-4 py-2 text-sm font-medium text-blue-900 hover:bg-blue-200">
            Got it, thanks!
         </button>
      </div>
   </div>
   <div class="bg-green-400 h-16"></div>

</template>

<script>
   export default {
      data: () => ({
         exibir: false,
         show: true,
      }),
   }
</script>