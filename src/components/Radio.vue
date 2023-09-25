<template>
   <div class="hidden lg:block">
      <Upside/>
   </div>
   <div class="lg:hidden">
      <UpSideMenu/>
   </div>
   <div class="h-screen text-slate-800 bg-gray-100 rounded dark:bg-slate-800 dark:text-white">
      <div class="mx-auto w-full max-w-md py-8">
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
                        {{ plan.ram }} {{ plan.cpus }}
                        <span aria-hidden="true"> &middot; </span>
                        {{ plan.disk }}
                     </li>
                  </ul>
               </div>
            </button>
            <div class="flex justify-end">
               <router-link to="/gpu">
                  <button class="dark:bg-slate-900 bg:gray-200 dark:text-gray-100 mt-3 font-medium py-2 px-5 mb-2 rounded-xl">
                     GPU
                  </button>
               </router-link>
            </div>
         </div>
      </div>
   </div>
</template>

<script>

export default {
   data: () => ({
      plans: [
         {
            name: 'Intel Core i7 3770K 3.2GHz',
            ram: '8GB',
            cpus: '4/8 CPU',
            disk: '240GB SSD',
         },
         {
            name: 'AMD Ryzen 5 5600G 3.4GHz',
            ram: '16GB',
            cpus: '6/12 CPU',
            disk: '480GB SSD',
         },
         {
            name: 'AMD Ryzen 7 5700X 3.8GHz',
            ram: '32GB',
            cpus: '8/16 CPU',
            disk: '1TB SSD',
         },
         {
            name: 'AMD Ryzen 9 5950X 4.6GHz',
            ram: '64GB',
            cpus: '12/24 CPU',
            disk: '2TB SSD',
         },
         {
            name: 'Intel Core i9 13900KS 5.0GHz',
            ram: '128GB',
            cpus: '20/40 CPU',
            disk: '4TB SSD',
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
document.title="Radio - Training"
</script>