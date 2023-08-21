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
                        {{ plan.ram }}/{{ plan.cpus }}
                        <span aria-hidden="true"> &middot; </span>
                        {{ plan.disk }}
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
            name: 'Startup',
            ram: '8GB',
            cpus: '4 CPUs',
            disk: '256 GB SSD disk',
         },
         {
            name: 'Business',
            ram: '16GB',
            cpus: '8 CPUs',
            disk: '512 GB SSD disk',
         },
         {
            name: 'Enterprise',
            ram: '32GB',
            cpus: '12 CPUs',
            disk: '1024 GB SSD disk',
         },
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