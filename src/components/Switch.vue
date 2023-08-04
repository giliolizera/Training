<template>
     <Switch
       v-model="enabled"
       :class="enabled ? 'bg-teal-900' : 'bg-teal-700'"
       class="relative inline-flex h-[18px] w-[34px] shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
     >
       <span
         aria-hidden="true"
         :class="enabled ? 'translate-x-3.5' : '-translate-x-0.5'"
         class="pointer-events-none inline-block h-[17px] w-[17px] transform rounded-full bg-white shadow-lg ring-0 transition duration-200 ease-in-out"
       />
     </Switch>
 </template>
 
 <script setup>
 import { ref } from 'vue'
 import { Switch } from '@headlessui/vue'
 
 const enabled = ref(false)
 </script>
 