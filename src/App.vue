<template>
  <Disclosure/>
  <Tabs/>
  <Select/>
  <Menu/>
  <Combobox/>
</template>

<script>
import Disclosure from './components/Disclosure.vue'
import Tabs from './components/Tabs.vue'
import Menu from './components/Menu.vue'
import Select from './components/Select.vue'
import Combobox from './components/Combobox.vue'

export default {
  components: {
    Disclosure, Tabs, Menu, Select, Combobox
  }
}
</script>

<style>

</style>
