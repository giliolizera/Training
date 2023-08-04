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
      <div class="col-span-2 grid lg:grid-cols-2 gap-4 pr-10 pl-2">
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
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 mt-1"
               v-model="form.senha">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Confirmar Senha
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 mt-1"
               v-model="form.confirmarSenha">
         </div>
         <div class="flex justify-end lg:col-span-2">
            <div>
                  <button @click="validar(), confereSenha(), trocarRota()"
                     class="bg-gray-200 hover:bg-gray-300 max-md:24 text-gray-900 font-medium text-sm py-2 px-6 rounded mt-3">
                     ENTRAR
                  </button>
            </div>
         </div>

      </div>
   </div>
</template>

<script>
export default {
   data: () => ({
      form: {
         nome: '',
         email: '',
         telefone: '',
         cpf: '',
         senha: '',
         confirmarSenha: ''
      },
      avançar: false,
      exibir: false,
   }),
   methods: {
      validar() {
         if (this.form.nome != '' && this.form.email != '' && this.form.telefone.length > 13 && this.form.cpf.length > 13) {
            this.avançar = true
            console.log('validar')
            console.log(this.avançar)
         }
         else {
            this.avançar = false
            console.log('validar')
            console.log(this.avançar)
         }
         
      },
      confereSenha() {
         if (this.form.senha != this.form.confirmarSenha || this.form.senha == '' || this.form.confirmarSenha == '') {
            this.exibir = false
            console.log('senha')
            console.log(this.exibir)
         }
         else {
            if (this.form.senha != '' && this.form.confirmarSenha != '') {
               this.exibir = true
               console.log('senha')
               console.log(this.exibir)
            }
         }
      },
      trocarRota() {
         if (this.exibir === true && this.avançar === true) {
            this.$router.push('/disclosure')
         }
      }
   },
}
</script>

<script setup>
   document.title = "Cadastro - Training"
</script>