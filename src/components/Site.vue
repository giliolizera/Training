<template>
   <div class="h-full">
      <div class="bg-slate-800 text-white">
         <div class="w-full bg-slate-900">
            <button class="text-blue-600 bg-slate-900 font-medium text-3xl flex p-4 justify-start">
               Training WebSite
            </button>
         </div>
         <div class="bg-slate-800 grid grid-cols-2 gap-4 p-2 mt-16 text-center">
            <div class="col-span-1 mt-2 text-xl text-white font-medium">
               Descubra as vantagens em utilizar o Traning para gerenciar seus negócios!
            </div>
            <div class="col-span-1 pr-10">
               <div>
                  <input type="text" class="w-full border bg-slate-700 rounded-md mt-2 p-2" placeholder="Nome">
               </div>
               <div>
                  <input type="email" class="w-full border bg-slate-700 rounded-md p-2 mt-2" placeholder="Email">
               </div>
               <router-link to="/login">
                  <button class="bg-blue-600 hover:bg-blue-700 text-white flex text-sm font-medium py-2 px-4 rounded mt-2">
                     Cadastrar
                  </button>
               </router-link>
            </div>
         </div>
         <div class="max-w-md mx-auto">
            <div class="text-center font-medium mt-6">
               O objetivo deste projeto é apenas treinar para aprender a usar o TailwindCSS e o Vue.JS
            </div>
            <div class="text-center font-medium mt-6">
               Para entrar anônimamente, clique no botão abaixo
            </div>
            <div class="flex justify-center mt-10">
               <router-link to="/disclosure">
                  <button class="bg-blue-600 hover:bg-blue-700 text-white text-sm font-medium py-2 px-4 rounded">
                     Entrar
                  </button>
               </router-link>
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
   </div>    
   <div class="bg-slate-800 h-12"></div>
</template>