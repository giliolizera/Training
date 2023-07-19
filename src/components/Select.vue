<template>
  <div class="bg-yellow-600 py-4">
     <div class="mx-auto w-72 max-w-md">
        <select class="flex w-full cursor-default rounded-lg bg-white py-2 pl-2 pr-10 text-left shadow-md focus:outline-none sm:text-sm font-medium ">
           <option class="bg-amber-100 text-amber-900 text-base hover:bg-amber-300 relative cursor-default select-none py-2 pl-10 pr-4" 
              v-for="people in peoples" :key="id">{{ people.name }}
           </option>
           <ChevronUpDownIcon class="h-5 w-5 text-gray-400"/>
        </select>
     </div>
  </div>
  <div class="h-64 bg-yellow-600"></div>
</template>

<script>
  import { ChevronUpDownIcon } from '@heroicons/vue/20/solid'

  export default {
     data: () => ({
        peoples: [
           { id: 1, name: 'Wade Cooper' },
           { id: 2, name: 'Arlene Mccoy' },
           { id: 3, name: 'Devon Webb' },
           { id: 4, name: 'Tom Cook' },
           { id: 5, name: 'Tanya Fox' },
           { id: 6, name: 'Hellen Schmidt' },
        ]
     })
  }
</script>