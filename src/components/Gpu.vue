<template>
   <div class="hidden lg:block">
      <Upside/>
   </div>
   <div class="lg:hidden">
      <UpSideMenu/>
   </div>
   <div class="text-slate-800 bg-gray-100 rounded dark:bg-slate-800 dark:text-white">
      <div class="flex justify-start">
         <router-link to="/radio">
            <button class="dark:bg-slate-900 bg-gray-200 dark:text-gray-100 ml-3 mt-3 font-medium py-2 px-5 mb-2 rounded-xl">
               Voltar para Radio
            </button>
         </router-link>
      </div>
      <div class="mx-auto w-full max-w-md">
         <div class="mx-auto w-full grid rounded-md">
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
                        {{ plan.vram }} vRAM
                        <span aria-hidden="true"> &middot; </span>
                        {{ plan.price }} R$
                     </li>
                  </ul>
               </div>
            </button>
         </div>
      </div>
   </div>
</template>


<script>

export default {
   data: () => ({
      plans: [
         {
            name: 'AMD Radeon RX 580',
            vram: '4GB',
            price: '399,00',
         },
         {
            name: 'Asus Nvidia GTX 1060',
            vram: '6GB',
            price: '499,00',
         },
         {
            name: 'AMD Challenger RX 6600',
            vram: '8GB',
            price: '1199,00',
         },
         {
            name: 'Gigabyte Nvidia RTX 4060 Ti',
            vram: '8GB',
            price: '2499,00',
         },
         {
            name: 'Saphire AMD RX 7800XT',
            vram: '12GB',
            price: '3799,00',
         },
         {
            name: 'Rog Strix Nvidia RTX 4090',
            vram: '24GB',
            price: '10.999,00',
         }
      ],
      active: -1,
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
document.title="Gpu - Training"
</script>