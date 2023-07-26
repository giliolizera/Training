<template>
   <div>
      <h1 class="text-blue-600 font-medium text-3xl flex mt-5 justify-center">Training WebSite</h1>
      <div>
         <div class="flex justify-center font-medium mt-10">
            Sobre Nós
         </div>
         <div class="flex justify-center font-medium mt-2">
            O objetivo deste projeto é apenas treinar para aprender a usar o TailwindCSS e o Vue.JS
         </div>
      </div>
      <div class="flex justify-center">
         <router-link to="/home">
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-10 ml-5">
            Home
            </button>
         </router-link> 
      </div>
      <div class="flex justify-center text-2xl mb-5 font-medium mt-10">
         Tecnologias usadas
      </div>
      <div class="flex justify-center font-medium mt-2">
         <div class="inline-flex space-x-2">
            <img src="../assets/logo.png" class="h-8 w-8">
            <p>Vue.JS</p>
         </div>
         <div class="inline-flex pl-4 space-x-2">
            <img src="../assets/tailwind.logo.png" class="h-7 w-7">
            <p>TailwindCSS</p>
         </div>
      </div>
   </div>
</template>