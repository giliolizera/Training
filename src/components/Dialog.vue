<template>
   <div class="bg-green-400 pt-24">
      <div class="inset-0 rounded-md flex items-center justify-center">
         <TransitionGroup
         enter-active-class="transition duration-500 ease-out"
         enter-from-class="opacity-0"
         enter-to-class="opacity-100"
         >
         <button v-if="show" @click="exibir = true" class="rounded-md bg-black bg-opacity-20 px-4 py-2 text-sm font-medium text-white hover:bg-opacity-30">
            Open Dialog
         </button>
         </TransitionGroup>
      </div>
      <TransitionGroup
        enter-active-class="transition duration-1000 ease-out"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-500 ease-in"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
         <div v-if="exibir" class="w-full max-w-md transform overflow-hidden rounded-2xl text-left shadow-xl transition-all bg-white p-4 space-y-2 items-center mx-auto">
            <p class="pl-1 font-medium">Payment Successful</p>
            <p class="pl-1 text-sm text-gray-500">Your payment has been successfully submitted. We`ve sent you an email with all of the details of your order.</p>
            <button @click="exibir = false, tempo()" class="inline-flex justify-center rounded-md border border-transparent bg-blue-200 px-4 py-2 text-sm font-medium text-blue-900 hover:bg-blue-200">
               Got it, thanks!
            </button>
         </div>
      </TransitionGroup>
   </div>
   <div class="bg-green-400 h-24"></div>

</template>

<script>
   export default {
      data: () => ({
         exibir: false,
         show: true,
      }),
      methods: {
         tempo() {
            setTimeout(() => {
               this.show = true;
            }, 600);
         },
      }
   }
</script>
