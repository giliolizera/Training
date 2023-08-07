<template>
  <Upside/>
  <div class="bg-gray-100 rounded dark:bg-slate-800 py-16">
    <div class="mx-auto w-72 max-w-md rounded-md">
      <div class="inline-flex bg-white text-black w-72 rounded-md">
        <input class="w-full bg-white pl-3 px-1 py-1 rounded-md focus:outline-none text-left" type="text"
         v-model="query"
         @keydown.prevent.esc="escape()"
         @keydown.prevent.down="baixo()" 
         @keydown.prevent.up="cima()" 
         @keydown.prevent.enter="enter()" 
         @keydown.prevent.backspace="backspace()" 
         />
        <button @click="exibir = !exibir"
         @keydown.prevent.esc="escape()" 
         @keydown.prevent.down="baixo()" 
         @keydown.prevent.up="cima()" 
         @keydown.prevent.enter="enter()"
         @keydown.prevent.backspace="backspace()" 
         class="px-1 py-1 rounded-md focus:outline-none" type="text"
         >
          <ChevronUpDownIcon class="h-5 w-5 text-gray-500"/> 
        </button>
      </div>
      <div class="mt-2 bg-white text-black grid rounded-md">
        <ul v-if="!exibir" class="pt-0.5 pb-0.5">
          <button @mouseenter="active = index " 
          @mouseleave="active = -1" 
          @click="selected = person.name, query = person.name, exibir=true"
          :class="[active === index
          ? 'bg-slate-400 rounded-md'
          : '', 'inline-flex py-1.5 w-full']" 
          v-for="(person,index) in filtredPeople" :key="index"
          >
          <div v-if="selected === person.name" class="pl-2 inline-flex">
            <CheckIcon class="h-5 w-5 mt-0.5 text-blue-500"/>
            <div class="pl-3">
              {{ person.name }} 
            </div>
          </div>
          <div v-if="selected !== person.name" class="pl-10">
            {{ person.name }} 
          </div>
          </button>
        </ul>
        <ul v-if="this.filtredPeopleLenght === 0">
          <div class="pl-10 p-1 pb-2 rounded-md">
            Nothing Found.
          </div>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  
  export default {  
    data() {
      return {
        query: '',
        people: [
          { id: 1, name: 'Durward Reynolds',},
          { id: 2, name: 'Kenton Towne', },
          { id: 3, name: 'Therese Wunsch',},
          { id: 4, name: 'Benedict Kessler',},
          { id: 5, name: 'Katelyn Rohan',},
          { id: 6, name: 'Wade Cooper',},
          { id: 7, name: 'Arlene Mccoy',},
          { id: 8, name: 'Devon Webb',},
          { id: 9, name: 'Tom Cook',},
          { id: 10, name: 'Hellen Schmidt',},
          { id: 11, name: 'Juarez Roberts'},
          { id: 12, name: 'Ronald Richards'},
          { id: 13, name: 'Suelen Bridger'},
          { id: 14, name: 'Felipe Gonzatt'},
          { id: 15, name: 'Roman Reynolds'},
          { id: 16, name: 'William Mccoy'},
          { id: 17, name: 'Peemi Cooper'},
          { id: 18, name: 'Celine Dept'},
        ],
        exibir: false,
        selected: 'Durward Reynolds',
        active: -1,
      }
    },
    component:{
      Upside
    },
    computed: {
      filtredPeople() {
        return this.query === ''
          ? this.people
          : this.people.filter((person) => {
              return person.name.toLowerCase().includes(this.query.toLowerCase())
            })
      },
      filtredPeopleLenght() {
        return this.query === ''
          ? this.people
          : this.cont = this.people.filter((person) => {
                 return person.name.toLowerCase().includes(this.query.toLowerCase())
               }).length
      }
    },
    methods: {
      baixo(){
        this.active++;
        if(this.active > this.people.length-1){
          this.active = 0;
        }
        if(this.active > this.filtredPeopleLenght-1){
          this.active = 0;
        }
      },
      cima() {
        this.active--;
        if(this.active < 0 && this.query === ''){
          this.active = this.people.length-1;
        }
        else if(this.active < 0){
          this.active = this.filtredPeopleLenght-1;
        }
      },
      escape() {
        this.exibir = true
      },
      enter(){
        let pessoa = this.filtredPeople[this.active]
        let id = pessoa.id -1
        this.exibir = true
        this.selected = this.people[id].name
        this.query = this.people[id].name
      },
      backspace(){
        this.query = this.query.slice(0, -1)
        this.exibir = false;
      }
    }
  }
</script>

<script setup>
  import Upside from './Upside.vue'
  import { ChevronUpDownIcon } from '@heroicons/vue/20/solid'
  import { CheckIcon } from "@heroicons/vue/24/outline";
  document.title = "Combobox - Training"
</script>