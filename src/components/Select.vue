<template>
  <div class="bg-orange-300 py-16">
    <div class="mx-auto w-72 max-w-md rounded-md">
      <div class="inline-flex bg-white w-72 rounded-md">
        <button @click="exibir = !exibir" @keypress="!exibir" @keydown.prevent.esc="escape()" @keydown.prevent.down="baixo()" @keydown.prevent.up="cima()" @keydown.prevent.enter="enter()" class="w-full pl-3 px-1 py-1 rounded-md text-left" type="text">{{ active }}</button>
        <button @click="exibir = !exibir">
          <ChevronUpDownIcon class="h-5 zw-5 text-gray-500"/> 
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
  <div class="h-4 bg-orange-300"></div>
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
     methods: {
        baixo() {
          for(let i=0 ; i<this.peoples.length ; i++) {
            if(this.active === this.peoples[i].name) {
              if(i === this.peoples.length-1) {
                this.active = this.peoples[0].name
                break
              }
              this.active = this.peoples[i+1].name
              break
            }
          }
        },
        cima() {
          for(let i=0 ; i<this.peoples.length ; i++) {
            if(this.active === this.peoples[i].name) {
              if(i === 0) {
                this.active = this.peoples[this.peoples.length-1].name
                break
              }
              this.active = this.peoples[i-1].name
              break
            }
          }
        },
        escape() {
          this.exibir = true
        },
        enter(){
          this.exibir = true
        }
  }
}
</script>

<script setup>
  import { ChevronUpDownIcon } from '@heroicons/vue/20/solid'
  import { CheckIcon } from "@heroicons/vue/24/outline";
</script>