<template>
  <div class="bg-orange-300 py-16">
    <div class="mx-auto w-72 max-w-md rounded-md">
      <div class="inline-flex bg-white w-72 rounded-md">
        <button @click="exibir = !exibir" @keydown.down="teste()" class="w-full pl-3 px-1 py-1 rounded-md text-left" type="text">{{ active }}</button>
        <button @click="exibir = !exibir">
          <ChevronUpDownIcon class="h-5 w-5 text-gray-500"/>
        </button>
      </div>
      
        <div class="mt-2">
          <ul v-if="!exibir" class="bg-white grid rounded-md">
              <button @click="active = people.name , exibir=true" class="inline-flex py-1.5 hover:bg-orange-200 hover:rounded-md" v-for="people in peoples" :key="id">
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
  <div class="h-4 bg-orange-300"></div>
</template>

<script>
  export default {
     data: () => ({
        peoples: [
           { id: 1, name: 'Wade Cooper' },
           { id: 2, name: 'Arlene Mccoy' },
           { id: 3, name: 'Devon Webb' },
           { id: 4, name: 'Tom Cook' },
           { id: 5, name: 'Tanya Fox' },
           { id: 6, name: 'Hellen Schmidt' },
        ],
        active: 'Wade Cooper',
        exibir: false,
     }),
     methods: {
        teste() {
          this.peoples.id = this.peoples.id + 1;
          console.log(this.peoples.id)
        }
     }
  }
</script>

<script setup>
  import { ChevronUpDownIcon } from '@heroicons/vue/20/solid'
  import { CheckIcon } from "@heroicons/vue/24/outline";
</script>