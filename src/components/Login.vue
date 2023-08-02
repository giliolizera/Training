<template>
   <head>
      <title>Training - Login</title>
   </head>
   <div class="w-full bg-slate-900">
      <router-link to="/">
         <button class="text-blue-600 bg-slate-900 font-medium text-3xl flex p-4 justify-start">
            Training WebSite
         </button>
      </router-link>
   </div>
   <div class="bg-slate-800 grid grid-cols-2 gap-4 p-2 text-center">
      <div class="col-span-1 mt-2 text-xl text-white font-medium">
         Junte-se conosco e descubra as vantagens em utilizar o Traning para gerenciar seus negócios!
      </div>
      <div class="col-span-1 pr-10">
         <div>
            <div class="text-white text-sm font-medium flex pl-1">
               Nome
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md mt-1 pl-3 p-2" v-model="form.nome" >
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Email
            </div>
            <input type="email" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 pl-3 mt-1" v-model="form.email">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               Telefone
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 pl-3 mt-1" v-model="form.telefone" v-maska="'(##) #####-####'">
         </div>
         <div>
            <div class="text-white text-sm font-medium flex pl-1 mt-2">
               CPF
            </div>
            <input type="text" class="w-full text-gray-200 border-blue-600 border bg-slate-700 rounded-md p-2 pl-3 mt-1" v-model="form.cpf"  v-maska="'###.###.###-##'">
         </div>
         <div class="flex justify-end">
            <router-link to="/disclosure">
               <button class="bg-gray-200 hover:bg-gray-300 max-md:24 text-gray-900 font-medium text-sm py-2 px-6 rounded mt-3">
                  ENTRAR
               </button>
            </router-link>
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
           senha: '',
           telefone: '',
           cpf: ''
       }
   })
}
</script>