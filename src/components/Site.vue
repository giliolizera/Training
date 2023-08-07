<template>
   <div class="h-full">
      <div class=" text-slate-800 bg-white rounded dark:bg-slate-800 dark:text-white">
         <div class="w-full bg-gray-200 dark:bg-slate-900">
            <button class="text-blue-600 bg-gray-200 dark:bg-slate-900 font-medium text-2xl flex p-4 justify-start">
               Training WebSite
            </button>
         </div>
         <div class="max-w-md mx-auto">
            <div class="text-center font-medium text-xl mt-6">
               O objetivo deste projeto é apenas treinar para aprender a usar o TailwindCSS e o Vue.JS
            </div>
            <div class="inline-flex p-10">
               <div class="ml-24">
                  <div class="text-center font-medium mt-6">
                     Para entrar anonimamente, <br> clique no botão abaixo
               </div>
               <div class="flex justify-center mt-2">
                  <router-link to="/disclosure">
                     <button class="dark:bg-gray-200 dark:hover:bg-gray-300 hover:bg-sky-600 bg-sky-800 text-white dark:text-gray-900 text-sm font-medium py-2 px-7 rounded">
                        ENTRAR
                     </button>
                  </router-link>
               </div>
               <div class="text-center font-medium mt-6">
                  Para cadastrar-se no sistema, <br> clique no botão abaixo
               </div>
               <div class="flex justify-center mt-2">
                  <router-link to="/cadastro">
                     <button class="dark:bg-gray-200 dark:hover:bg-gray-300 hover:bg-sky-600 bg-sky-800 text-white dark:text-gray-900 text-sm font-medium py-2 px-5 rounded">
                        CADASTRAR
                     </button>
                  </router-link>
               </div>
            </div>
         </div>
         
         <div class="flex justify-center text-xl mb-5 font-medium mt-10">
            Tecnologias utilizadas no projeto
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
   </div>
</template>

<style>
::-webkit-scrollbar {
   width: 8px;
   height: 2px;
   /* A altura só é vista quando a rolagem é horizontal */
}

::-webkit-scrollbar-track {
   background: #000;
   padding: 2px;
}

::-webkit-scrollbar-thumb {
   background-color: #393939;
}
</style>

<script setup>
   document.title = "Home - Training"
</script>