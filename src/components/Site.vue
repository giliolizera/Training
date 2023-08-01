<template>
   <div class="h-full">
      <div class="bg-slate-800 text-white">
         <div class="w-full bg-slate-900">
            <button class="text-blue-600 bg-slate-900 font-medium text-3xl flex p-4 justify-start">
               Training WebSite
            </button>
         </div>
         <div class="max-w-md mx-auto">
            <div class="text-center font-medium text-xl mt-6">
               O objetivo deste projeto é apenas treinar para aprender a usar o TailwindCSS e o Vue.JS
            </div>
         </div>
            <div class="grid grid-cols-2 p-10">
               <div class="col-span-1 ml-48">
                  <div class="text-center font-medium mt-6">
                     Para entrar anônimamente, clique no botão abaixo
                  </div>
                  <div class="flex justify-center mt-2">
                     <router-link to="/disclosure">
                        <button class="bg-blue-600 hover:bg-blue-700 text-white text-sm font-medium py-2 px-4 rounded">
                           Entrar
                        </button>
                     </router-link>
                  </div>
               </div>   
               <div class="col-span-1 mr-48">
                  <div class="text-center font-medium mt-6">
                     Para cadastrar uma conta, clique no botão abaixo
                  </div>
                  <div class="flex justify-center mt-2">
                     <router-link to="/login">
                        <button class="bg-blue-600 hover:bg-blue-700 text-white text-sm font-medium py-2 px-4 rounded">
                           Cadastrar
                        </button>
                     </router-link>
                  </div>
               </div>
            </div>

            <div class="flex justify-center text-xl mb-5 font-medium mt-10">
               Tecnologias utilizadas
            </div>
            <div class="flex justify-center mt-2">
               <div class="inline-flex space-x-2">
                  <img src="../assets/logo.png" class="h-7 w-7">
                  <p>Vue.JS</p>
               </div>
               <div class="inline-flex pl-4 space-x-2">
                  <img src="../assets/tailwind.logo.png" class="h-7 w-7">
                  <p>TailwindCSS</p>
               </div>
            </div>
         </div>
      </div>  
      <div class="bg-slate-800 h-48"></div>
</template>

<style>
::-webkit-scrollbar {
  width: 8px;
  height: 2px; /* A altura só é vista quando a rolagem é horizontal */
}

::-webkit-scrollbar-track {
  background: #000;
  padding: 2px;
}

::-webkit-scrollbar-thumb {
  background-color: #393939;
}
</style>
