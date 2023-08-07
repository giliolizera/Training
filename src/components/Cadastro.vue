<template>
   <div class=" text-slate-800 bg-white rounded dark:bg-slate-800 dark:text-white">
      <div class="w-full bg-gray-200 dark:bg-slate-900 inline-flex">
         <router-link to="/">
            <button class="text-blue-600 bg-gray-200 dark:bg-slate-900 font-medium text-2xl flex p-4 justify-start">
               Training WebSite
            </button>
         </router-link>
         <Switch class="mt-6"/>
      </div>
      <div class="grid grid-cols-1 gap-4 p-2 pl-2.5 pl- text-center lg:grid-cols-3 md:grid-cols-3">
         <div class="col-span-1 mt-4 text-lg font-medium">
            Junte-se conosco e descubra as vantagens em utilizar o Traning para gerenciar seus negócios!
         </div>
         <form class="col-span-2 grid lg:grid-cols-2 gap-4 pr-2 pl-2">
            <div>
               <div class="text-sm font-medium flex pl-1 mt-2">
                  Nome
               </div>
               <input type="text" class="w-full dark:text-gray-200 dark:border-blue-600 border-black border dark:bg-slate-700 bg-white rounded-md mt-1 pl-3 p-2"
                  v-model="form.nome">
            </div>
            <div>
               <div class="text-sm font-medium flex pl-1 mt-2">
                  Email
               </div>
               <input type="email" class="w-full dark:text-gray-200 dark:border-blue-600 border-black border dark:bg-slate-700 bg-white rounded-md p-2 pl-3 mt-1"
                  v-model="form.email">
            </div>
            <div>
               <div class="text-sm font-medium flex pl-1 mt-2">
                  Telefone
               </div>
               <input type="text" class="w-full dark:text-gray-200 dark:border-blue-600 border-black border dark:bg-slate-700 bg-white rounded-md p-2 mt-1"
                  v-model="form.telefone" v-maska="'(##) #####-####'">
            </div>
            <div>
               <div class="text-sm font-medium flex pl-1 mt-2">
                  CPF
               </div>
               <input type="text" class="w-full dark:text-gray-200 dark:border-blue-600 border-black border dark:bg-slate-700 bg-white rounded-md p-2 mt-1"
                  v-model="form.cpf" v-maska="'###.###.###-##'">
            </div>
            <div>
               <div class="text-sm font-medium flex pl-1 mt-2">
                  Senha
               </div>
               <div class="relative w-full">
                  <input :type="typePassword ? 'password' : 'text'"
                     class="w-full dark:text-gray-200 dark:border-blue-600 border-black border dark:bg-slate-700 bg-white rounded-md p-2 mt-1"
                     v-model="form.senha">
                  <button class="absolute inset-y-0 right-0 pt-1 pr-3" @click.prevent.stop="typePassword = !typePassword">
                     <EyeIcon v-if="typePassword" class="h-5 w-5 text-neutral-500" />
                     <EyeSlashIcon v-if="!typePassword" class="h-5 w-5 text-neutral-500" />
                  </button>
               </div>
            </div>
            <div class="flex justify-end lg:col-span-2">
               <div>
                  <button @click="validar(), trocarRota()"
                     class="dark:bg-gray-200 bg-sky-800 text-white hover:bg-gray-300 max-md:24 dark:text-gray-900 font-medium text-sm py-2 px-6 rounded mt-3">
                     ENTRAR
                  </button>
               </div>
            </div>

         </form>
      </div>
   </div>
</template>

<script>
import { EyeIcon, EyeSlashIcon } from "@heroicons/vue/24/outline"
import Switch from '../components/Switch.vue'

export default {
   data: () => ({
      form: {
         nome: '',
         email: '',
         telefone: '',
         cpf: '',
         senha: '',
      },
      avançar: false,
      exibir: false,
      typePassword: true,
   }),
   methods: {
      validar() {
         if (this.form.nome != '' && this.form.email.length > 10 && this.form.telefone.length > 13 && this.form.cpf.length > 13 && this.form.senha.length > 5) {
            this.avançar = true
         }
         else {
            this.avançar = false
         }
      },
      trocarRota() {
         if (this.avançar) {
            this.$router.push('/disclosure')
         }
      }
   },
   components: {
      Switch,
   }
}
</script>

<script setup>
   document.title = "Cadastro - Training"
</script>