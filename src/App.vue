<template>
  <nav-bar @change-component="updateSelectedComponent"></nav-bar>
</template>

<script>
import NavBar from "./components/navigation/NavBar.vue";

export default {
  name: "App",
  components: {
    NavBar,
  },
};
</script>

<style>
</style>
