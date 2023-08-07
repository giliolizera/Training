<template>
   <div class="w-full bg-slate-900">
      <router-link to="/">
         <button class="text-blue-600 bg-slate-900 font-medium w-auto text-2xl flex p-4 justify-start">
            Training WebSite
         </button>
      </router-link>
   </div>
   <div class="bg-slate-800 grid grid-cols-1 gap-4 p-2 text-center lg:grid-cols-3 md:grid-cols-3">
      <div class="col-span-1 mt-4 text-lg text-white font-medium">
         Junte-se conosco e descubra as vantagens em utilizar o Traning para gerenciar seus negócios!
      </div>
      <form class="col-span-2 grid lg:grid-cols-2 gap-4 pr-10 pl-2">
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Nome
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md mt-1 pl-3 p-2"
               v-model="form.nome">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Email
            </div>
            <input type="email" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 pl-3 mt-1"
               v-model="form.email">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Telefone
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 mt-1"
               v-model="form.telefone" v-maska="'(##) #####-####'">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               CPF
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 mt-1"
               v-model="form.cpf" v-maska="'###.###.###-##'">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Senha
            </div>
            <div class="relative w-full">
               <input :type="typePassword ? 'password' : 'text'"
                  class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 mt-1"
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
                  class="bg-gray-200 hover:bg-gray-300 max-md:24 text-gray-900 font-medium text-sm py-2 px-6 rounded mt-3">
                  ENTRAR
               </button>
            </div>
         </div>

      </form>
   </div>
</template>

<script>
import { EyeIcon, EyeSlashIcon } from "@heroicons/vue/24/outline"

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
         if (this.form.nome != '' && this.form.email > 10 && this.form.telefone.length > 13 && this.form.cpf.length > 13 && this.form.senha > 5) {
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
}
</script>

<script setup>
   document.title = "Cadastro - Training"
</script>