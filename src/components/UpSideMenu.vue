<template>
   <div>
         <div class="flex justify-between p-4 bg-gray-200 dark:bg-slate-900">
            <router-link to="/">
               <button class="text-blue-600 bg-gray-200 dark:bg-slate-900 font-medium text-2xl justify-start">
                  Training WebSite
               </button>
            </router-link>
            <button @click="exibeMenu()">
               <EllipsisVerticalIcon class="h-6 w-6 text-white" />
            </button>
         </div>
         <div class="inline-grid" v-if="exibir">
            <router-link to="/disclosure">
                  Disclosure
            </router-link>
            <router-link to="/tabs">
                  Tabs
            </router-link>
            <router-link to="/select">
                  Select
            </router-link>
            <router-link to="/menu">
                  Menu
            </router-link>
            <router-link to="/combobox">
                  Combobox
            </router-link>
            <router-link to="/dialog">
               Dialog
            </router-link>
            <router-link to="/popover">
                  Popover
            </router-link>
            <router-link to="/radio">
                  Radio
            </router-link>
            <div class="ml-2 mt-5">
               <Switch/>
            </div>
         </div>
      </div>
</template>

<script>
import { EllipsisVerticalIcon } from "@heroicons/vue/24/outline";
import Switch from './Switch.vue'
export default {
   components: {
      EllipsisVerticalIcon, Switch
   },
   exibir: false,
   methods: {
      exibeMenu() {
         this.exibir = !this.exibir
         console.log(this.exibir)
      }
   }
}
</script>



