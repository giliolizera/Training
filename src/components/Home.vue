<template>
   <Upside/>
   <Disclosure/>
   <Tabs/>
   <Select/>
   <Menu/>
   <Combobox/>
   <Dialog/>
   <Radio/>
   <Popover/>
   <Baseboard/>
 </template>
 
 <script>
 import Upside from './Upside.vue'
 import Disclosure from './Disclosure.vue'
 import Tabs from './Tabs.vue'
 import Menu from './Menu.vue'
 import Select from './Select.vue'
 import Combobox from './Combobox.vue'
 import Dialog from './Dialog.vue'
 import Radio from './Radio.vue'
 import Popover from './Popover.vue'
 import Baseboard from './Baseboard.vue'
 
 export default {
   components: {
     Disclosure, Tabs, Menu,
     Select, Combobox, Dialog, 
     Radio, Popover, Upside, Baseboard
   }
 }
 </script>
 
 <style>
 
 </style>
 