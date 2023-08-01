<template>
   <div class="w-full bg-slate-900">
      <router-link to="/">
         <button class="text-blue-600 bg-slate-900 font-medium text-3xl flex p-4 justify-start">
            Training WebSite
         </button>
      </router-link>
   </div>
   <div class="bg-slate-800 grid grid-cols-2 gap-4 p-2 text-center">
      <div class="col-span-1 mt-2 text-xl text-white font-medium">
         Descubra as vantagens em utilizar o Traning para gerenciar seus negócios!
      </div>
      <div class="col-span-1 pr-10">
         <div>
            <input type="text" class="w-full border bg-slate-700 rounded-md mt-2 p-2" v-model="form.nome" placeholder="Nome">
         </div>
         <div>
            <input type="email" class="w-full border bg-slate-700 rounded-md p-2 mt-2" v-model="form.email" placeholder="Email">
         </div>
         <div>
            <input type="text" class="w-full border bg-slate-700 rounded-md p-2 mt-2" v-model="form.telefone" placeholder="Telefone" v-maska="'(##) #####-####'">
         </div>
         <div>
            <input type="text" class="w-full border bg-slate-700 rounded-md p-2 mt-2" v-model="form.cpf" placeholder="CPF" v-maska="'###.###.###-##'">
         </div>
         <router-link to="/disclosure">
            <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-2">
               Me inscrever
            </button>
         </router-link>
      </div>
   </div>
   <div class="bg-slate-800 h-72"></div>
</template>

<script>
export default {
   data: () => ({
       form: {
           nome: '',
           email: '',
           senha: '',
           telefone: '',
           cpf: ''
       }
   })
}
</script>