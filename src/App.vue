<template>
  <nav-menu />
  <router-view />
</template>

<script>
import NavMenu from "./components/global/NavMenu";

export default {
  name: "App",
  components: {
    NavMenu,   
  },
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>
