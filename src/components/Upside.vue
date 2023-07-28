<template>
   <div class="flex justify-start bg-slate-900">
      <router-link to="/">
         <button class="text-blue-600 bg-slate-900 font-medium text-3xl flex p-4 justify-start">
            Training WebSite
         </button>
      </router-link>
      <router-link to="/disclosure" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
            Disclosure
         </button>
      </router-link> 
      <router-link to="/tabs" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
            Tabs   
         </button>
      </router-link>
      <router-link to="/select" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
            Select
         </button>
      </router-link>
      <router-link to="/menu" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
         Menu
         </button>
      </router-link>
      <router-link to="/combobox" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
         Combobox
         </button>
      </router-link>
      <router-link to="/dialog" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
         Dialog
         </button>
      </router-link>
      <router-link to="/popover" class="m-2 mt-3.5">
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
         Popover
      </button>
      </router-link>
      <router-link to="/radio" class="m-2 mt-3.5"  >
         <button class="bg-slate-600 hover:bg-slate-700 text-white font-bold py-2 px-4 rounded-xl">
         Radio
         </button>
      </router-link>
   </div>
</template>