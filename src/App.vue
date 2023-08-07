<script setup>

import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)

</script>
<template>
  <div class="h-screen w-screen overflow-auto bg-slate-800">
    {{ isDark }}
    <button @click="toggleDark()" class="px-4 py-2 text-slate-800 bg-white-500 rounded dark:bg-slate-800 dark:text-white">Toggle Dark</button>
    <router-view/>
  </div>
</template>

<style>

html.dark {
  color-scheme: dark;
}

</style>