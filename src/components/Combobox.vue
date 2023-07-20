<template>
   <div class="py-16 bg-blue-500">
     <div class="mx-auto w-72 max-w-md rounded-md">
       <div class="inline-flex bg-white w-72 rounded-md">
         <input class="w-full pl-3 px-1 py-1 rounded-md text-left" type="text" v-model="active">
         <button @click="exibir = !exibir">
            <ChevronUpDownIcon class="h-5 w-5 text-gray-500"/>
         </button>
       </div>
       
         <div class="mt-2">
           <ul v-if="!exibir" class="bg-white grid rounded-md">
               <button @click="active = people.name , exibir=true" class="inline-flex py-1.5 hover:bg-orange-200 hover:rounded-md" v-for="(people,index) in peoples" :key="index">
                 <div v-if="active === people.name" class="pl-2 inline-flex">
                   <CheckIcon class="h-5 w-5 mt-0.5 text-yellow-500"/>
                   <div class="pl-3">
                     {{ people.name }}
                   </div>
                 </div>
                 <div v-if="active != people.name" class="pl-10">
                   {{ people.name }}
                 </div>
               </button>
           </ul>
         </div>
      </div>
 
   </div>
   <div class="h-40 bg-blue-500"></div>
 </template>
 
 <script>
   export default {
      data: () => ({
         peoples: [
            { name: 'Wade Cooper' },
            { name: 'Arlene Mccoy' },
            { name: 'Devon Webb' },
            { name: 'Tom Cook' },
            { name: 'Tanya Fox' },
            { name: 'Hellen Schmidt' },
         ],
         active: 'Wade Cooper',
         exibir: true,
      }),
      watch: {
        filtrar(){
          this.peoples = this.peoples.filter(people => people.name.includes(this.filtrar))
        }
      }
   }
 </script>
 
 <script setup>
   import { ChevronUpDownIcon } from '@heroicons/vue/20/solid'
   import { CheckIcon } from "@heroicons/vue/24/outline";
 </script>