<template>
   <div class="hidden lg:block">
      <Upside/>
   </div>
   <div class="lg:hidden">
      <UpSideMenu/>
   </div>
   <div class="text-slate-800 bg-gray-100 rounded dark:bg-slate-800 dark:text-white">
      <div class="mx-auto w-full max-w-md py-8">
         <div v-if="!exibir" class="mx-auto w-full grid rounded-md">
            <button v-for="(plan, index) in plans" :key="index" @click="active = plan.name">
               <div
                  :class="[active === plan.name ? 'dark:bg-slate-900 bg-gray-500 ring-2 ring-white ring-opacity-60 ring-offset-2 ring-offset-slate-600 text-white' : 'bg-white text-black', 'mx-auto w-full max-w-md rounded-md px-5 py-4 mt-3']">
                  <ul class="justify-between flex">
                     <li class="text-left text-sm font-medium">
                        {{ plan.name }}
                     </li>
                     <button v-if="active === plan.name" class="absolute pl-96">
                        <CheckCircleIcon class="hidden sm:block h-8 w-8 mt-1 text-black-500" />
                     </button>
                  </ul>
                  <ul>
                     <li
                        :class="[active === plan.name ? 'static text-left text-sm text-gray' : 'static text-left text-sm text-gray-600']">
                        {{ plan.ram }} RAM
                        <span aria-hidden="true"> &middot; </span>                        
                        {{ plan.cpus }}
                        <span aria-hidden="true"> &middot; </span>
                        {{ plan.price }} R$
                     </li>
                  </ul>
               </div>
            </button>
         </div>
      </div>
   </div>
   <div class="flex justify-end">
         <button @click="exibir = true" class="dark:bg-slate-900 bg-gray-200 text-black dark:text-gray-100 mt-3 font-medium py-2 px-5 rounded-xl">
            GPU
         </button>
         <div v-if="exibir">
            <Gpu />
         </div>
   </div>
</template>


<script>

export default {
   data: () => ({
      props:{
         exibir: Boolean,
      },
      plans: [
         {
            name: 'Intel Core i5 3470 3.60GHz',
            ram: '8GB',
            cpus: '4/4 CPU',
            price: '139,99',
         },
         {
            name: 'Intel Core i7 4770K 3.90GHz',
            ram: '8GB',
            cpus: '4/8 CPU',
            price: '269,99',
         },
         {
            name: 'AMD Ryzen 5 5600G 4.40GHz',
            ram: '16GB',
            cpus: '6/12 CPU',
            price: '899,99',
         },
         {
            name: 'AMD Ryzen 7 5700X 4.60GHz',
            ram: '32GB',
            cpus: '8/16 CPU',
            price: '1249,99',
         },
         {
            name: 'AMD Ryzen 9 5950X 4.9GHz',
            ram: '64GB',
            cpus: '16/32 CPU',
            price: '3299,99',
         },
         {
            name: 'Intel Core i9 13900KS 6.0GHz',
            ram: '64GB',
            cpus: '24/32 CPU',
            price: '4999,99',
         }
      ],
      active: -1,
      exibir: false,
   }),
   components: {
      Upside, UpSideMenu
   },
}

</script>

<script setup>
import { CheckCircleIcon } from "@heroicons/vue/24/outline";
import Upside from "./Upside.vue";
import UpSideMenu from "./UpSideMenu.vue";
import Gpu from "./Gpu.vue";
document.title="Radio - Training"
</script>