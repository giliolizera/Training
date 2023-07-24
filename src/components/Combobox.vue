<template>
  <div class="bg-slate-600 py-16">
    <div class="mx-auto w-72 max-w-md rounded-md">
      <div class="inline-flex bg-white w-72 rounded-md">
        <input class="w-full pl-3 px-1 py-1 rounded-md focus:outline-none text-left" 
        :displayValue="selected" 
        v-model="query" 
         @keypress="!exibir" 
         @keydown.prevent.esc="escape()" 
         @keydown.prevent.down="baixo()" 
         @keydown.prevent.up="cima()" 
         @keydown.prevent.enter="enter()" 
        />
        <button @click="exibir = !exibir"
         @keypress="!exibir" 
         @keydown.prevent.esc="escape()" 
         @keydown.prevent.down="baixo()" 
         @keydown.prevent.up="cima()" 
         @keydown.prevent.enter="enter()" 
         class="px-1 py-1 rounded-md focus:outline-none" type="text"
         >
          <ChevronUpDownIcon class="h-5 w-5 text-gray-500"/> 
        </button>
      </div>
      <div class="mt-2 bg-white grid rounded-md">
        <ul v-if="!exibir">
          <button @mouseenter="active = person.id" 
          @mouseleave="active = -1" 
          @click="selected = person.name , exibir=true"
          :class="[active === person.id 
          ? 'bg-blue-200 rounded-md'
          : '', 'inline-flex py-1.5 w-full']" 
          v-for="person in filtredPeople" :key="person.id"
          >
          <div v-if="selected === person.name" class="pl-2 inline-flex">
            <CheckIcon class="h-5 w-5 mt-0.5 text-blue-500"/>
            <div class="pl-3">
              {{ person.name }} - {{ person.status ? "ON" : "OFF" }}
            </div>
          </div>
          <div v-if="selected != person.name" class="pl-10">
            {{ person.name }} - {{ person.status ? "ON" : "OFF" }}
          </div>
          </button>
        </ul>
      </div>
    </div>
  </div>
  <div class="h-4 bg-slate-600"></div>
</template>

<script>
  export default {
    data() {
      return {
        query: '',
        people: [
          { id: 1, name: 'Durward Reynolds', status: true },
          { id: 2, name: 'Kenton Towne', status: false },
          { id: 3, name: 'Therese Wunsch', status: false },
          { id: 4, name: 'Benedict Kessler', status: true },
          { id: 5, name: 'Katelyn Rohan', status: false },
          { id: 6, name: 'Wade Cooper', status: true },
          { id: 7, name: 'Arlene Mccoy', status: false },
          { id: 8, name: 'Devon Webb', status: true },
          { id: 9, name: 'Tom Cook', status: true },
          { id: 10, name: 'Tanya Fox', status: false },
          { id: 11, name: 'Hellen Schmidt', status: false },
        ],
        exibir: false,
        selected: 'Wade Cooper',
        active: -1,
      }
    },
    computed: {
      filtredPeople() {
        return this.query === ''
          ? this.people
          : this.people.filter((person) => {
              return person.name.toLowerCase().includes(this.query.toLowerCase())
            })
      }
    },
    methods: {
      baixo(){
        this.active++;
        if(this.active > this.people.length-1){
          this.active = 0;
        }
      },
      cima() {
        this.active--;
        if(this.active < 0){
          this.active = this.people.length-1;
        }
      },
      escape() {
        this.exibir = true
      },
      enter(){
        this.exibir = true
        this.selected = this.people[this.active].name
      },
    }
  }
</script>

<script setup>
  import { ChevronUpDownIcon } from '@heroicons/vue/20/solid'
  import { CheckIcon } from "@heroicons/vue/24/outline";
</script> 