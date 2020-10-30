<template>
  <nav-bar
    @change-component="updateSelectedComponent"
  ></nav-bar>

  <keep-alive>
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @update-current="updateCurrent"
    >
    </component>
  </keep-alive>
  
</template>

<script>
import LeconList from './components/LeconList.vue'
import CurrentList from './components/CurrentList.vue'

import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    LeconList,
    NavBar,
    CurrentList
  },
  data() {
    return {
      selectedComponent: 'lecon-list',
      currentArray: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "current-list") {
        return { current: this.currentArray }
      }
      return false
    }
  },
  methods: {
    updateSelectedComponent(comp) {
      this.selectedComponent = comp
    },
    updateCurrent(lecon) {
      this.currentArray.push(lecon)
    }
  }
}
</script>
<style>

</style>
