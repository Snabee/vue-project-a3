<template>
  <div
    class="max-w-sm rounded overflow-hidden shadow-lg px-6 py-4 m-5 flex justify-between"
    :class="isInjuredClass"
  >
    <div>
      <h3 class="font-bold text-xl mb-2">
        {{ playerName }} ({{ player.number }})
      </h3>
      <p class="text-gray-700 text-base">{{ player.position }}</p>
    </div>
    <base-button text="Sélectionner" @click="addToSelection"></base-button>
  </div>
</template>

<script>
export default {
  name: "player-card",
  props: ["player"],
  computed: {
    playerName() {
      if (this.player.name.split(".").length > 1) {
        return this.player.name.split(".")[1];
      }
      return this.player.name;
    },
    playerInjured() {
      if (this.player.health == "out") {
        return true;
      }
      return false;
    },
    isInjuredClass() {
      return {
        "bg-red-500 text-white": this.playerInjured,
        "bg-green-500 text-white": !this.playerInjured,
      };
    },
  },
  methods: {
      addToSelection() {
          this.$emit('add-player', this.player)
      }
  },
};
</script>

<style scoped>
</style>