<template>
   <div class="flex justify-center">
      <ChevronUpDownIcon
         class="h-5 w-5 text-gray-400"
      />
      <select class="form-select">
         <option v-for="people in peoples" :key="id">{{ people.name }}</option>
      </select>
   </div>
   <div class="h-24 bg-dark"></div>
</template>

<script>

   import { ChevronUpDownIcon } from '@heroicons/vue/24/outline'

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