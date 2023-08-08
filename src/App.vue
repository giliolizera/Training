<template>
  <div class="h-screen w-screen overflow-auto dark:bg-slate-800 bg-white">
    <!-- <UpSideMenu/> -->
    <router-view/>
  </div>
</template>

<style>

html.dark {
  color-scheme: dark;
}

</style>

<script>
  import UpSideMenu from './components/UpSideMenu.vue'

  export default{
    components: {
      UpSideMenu
    }
  }
</script>