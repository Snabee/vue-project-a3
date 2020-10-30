<template>
  <h1 class="m-10 ml-10 pl-5 font-bold text-xl">Liste des {{ leconsData.name }}</h1>

  <current-box :current="current"> </current-box>

  <div class="flex flex-wrap items-center mx-10">
    <lecon-card
      v-for="(lecon, index) in leconsData.lecons"
      :key="index"
      :lecon="lecon"
      @add-lecon="addLeconToCurrent"
      class="w-1/3 px-2 m-5"
    >
    </lecon-card>
  </div>
</template>

<script>
import leconsData from "../assets/data/lecons.json";
import LeconCard from "./LeconCard.vue";

export default {
  name: "lecon-List",
  components: {
    LeconCard,
  },
  data() {
    return {
      leconsData: leconsData,
      current: [],
    };
  },
  methods: {
    addLeconToCurrent(lecon) {
      this.current.push(lecon);
      this.$emit("update-current", lecon);
    },
  },
};
</script>

<style>
</style>