<template>
   <Disclosure/>
   <Tabs/>
   <Select/>
   <Menu/>
   <Combobox/>
   <Dialog/>
   <Radio/>
   <Popover/>
 </template>
 
 <script>
 import Disclosure from './Disclosure.vue'
 import Tabs from './Tabs.vue'
 import Menu from './Menu.vue'
 import Select from './Select.vue'
 import Combobox from './Combobox.vue'
 import Dialog from './Dialog.vue'
 import Radio from './Radio.vue'
 import Popover from './Popover.vue'
 
 export default {
   components: {
     Disclosure, Tabs, Menu,
     Select, Combobox, Dialog, 
     Radio, Popover
   }
 }
 </script>
 
 <style>
 
 </style>
 