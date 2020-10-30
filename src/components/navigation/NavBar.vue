<template>
  <nav class="flex items-center justify-between flex-wrap bg-white-500 p-6 border-b shadow">
    <div class="flex items-center flex-shrink-0 text-black mr-6">
      <img :src="myLogo" alt="" class="h-8 mr-12" />
    </div>
    <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
      <div class="text-sm lg:flex-grow">
        <a
          v-for="(link, index) in navigation"
          :key="index"
          href="#"
          @click="selectComponent(link.component)"
          class="block mt-4 lg:inline-block lg:mt-0 text-black-200 mr-4"
        >
          {{ link.name }}
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "nav-bar",
  data() {
    return {
      navigation: [
        { name: "Cours", component: "lecon-list" },
        { name: "Profil", component: "current-list" },
      ],
      myLogo: require('../../assets/img/logo.svg'),
    };
  },
  methods: {
    selectComponent(comp) {
      this.$emit("change-component", comp);
    },
  },
};
</script>

<style>
</style>