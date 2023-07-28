<template>
   <div class="h-full">
   <div class="bg-slate-800 text-white">
      <div class="w-full bg-slate-900">
         <button class="text-blue-600 bg-slate-900 font-medium text-3xl flex p-4 justify-start">
            Training WebSite
         </button>
      </div>
      <div class="max-w-md mx-auto">
         <div class="flex justify-center font-bold text-xl mt-8">
            Sobre Nós
         </div>
         <div class="text-center font-medium mt-3">
            O objetivo deste projeto é apenas treinar para aprender a usar o TailwindCSS e o Vue.JS
         </div>
      </div>
      <div class="flex justify-center mt-10">
         <router-link to="/disclosure">
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Go to project
            </button>
         </router-link> 
      </div>
      <div class="flex justify-center text-xl mb-5 font-medium mt-10">
         Tecnologias usadas
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
   <div class="bg-slate-800 h-72"></div>
</template>