<script setup>
import Switch from './components/Switch.vue'
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)

</script>
<script>
export default {
  components: {
    Switch
  }
}
</script>

<template>
  <div class="h-screen w-screen overflow-auto dark:bg-slate-800 bg-white">
    <Switch @click="toggleDark()" class="flex">
      Toggle Dark
    </Switch>
    <router-view/>
  </div>
</template>

<style>

html.dark {
  color-scheme: dark;
}

</style>