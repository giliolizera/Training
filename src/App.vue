<template>
  <Disclosure/>
  <Tabs/>
  <Select/>
  <Menu/>
  <Combobox/>
  <Dialog/>
  <!-- <ComboHead/> -->
</template>

<script>
import Disclosure from './components/Disclosure.vue'
import Tabs from './components/Tabs.vue'
import Menu from './components/Menu.vue'
import Select from './components/Select.vue'
import Combobox from './components/Combobox.vue'
import Dialog from './components/Dialog.vue'
import ComboHead from './components/ComboHead.vue'

export default {
  components: {
    Disclosure, Tabs, Menu,
    Select, Combobox, Dialog, ComboHead
  }
}
</script>

<style>

</style>
