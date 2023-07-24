<template>
 <div class="pt-10 flex justify-center pl-10 bg-purple-500">
   <div class="relative inline-block">
      <button @click="exibir = !exibir" class="inline-flex w-full justify-center rounded-md bg-purple-600 px-4 py-2 text-sm font-medium text-white hover:bg-opacity-60">
         Options
         <ChevronDownIcon class="ml-2 -mr-1 h-5 w-5 text-violet-200 hover:text-violet-100"/>
      </button>      
   </div>
 </div>
 <div class="h-64 bg-purple-500"></div>

</template>

<script>
   export default {
      data:() => ({
         exibir: true,
      }),
   }
</script>

<script setup>
   import { ChevronDownIcon } from "@heroicons/vue/24/outline";
</script>