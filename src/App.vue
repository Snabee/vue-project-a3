<template>
  <nav-bar @change-component="updateSelectedComponent"></nav-bar>
  <keep-alive>
    <component :is="selectedComponent" v-bind="currentProps"></component>
  </keep-alive>
</template>

<script>
import PlayerList from "./components/PlayerList.vue";
import SelectionList from "./components/SelectionList.vue";
import NavBar from "./components/navigation/NavBar.vue";

export default {
  name: "App",
  components: {
    PlayerList,
    NavBar,
    SelectionList,
  },
  data() {
    return {
      selectedComponent: "player-list",
    };
  },
  computed: {
    currentProps() {
      if (this.selectedComponent == "selection-list") {
        return { selection: this.selectedComponent };
      }
      return false;
    },
  },
  methods: {
    updateSelectedComponent(comp) {
      this.selectedComponent = comp;
    },
  },
};
</script>

<style>
</style>
