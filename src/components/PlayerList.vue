<template>
  <div class="main">
    <h1 class="font-bold text-xl mb-2">
      Liste des joueurs {{ playersData.name }}
    </h1>

    <player-selection :selection="selection"></player-selection>

    <player-card
      v-for="(player, index) in playersData.players"
      :key="index"
      :player="player"
      @add-player="addPlayerToSelection"
    ></player-card>
  </div>
</template>

<script>
import PlayerCard from "./PlayerCard.vue";
import PlayerSelection from "./PlayerSelection.vue";
import playersData from "../assets/data/players.json";

export default {
  name: "player-list",
  components: {
    PlayerCard,
    PlayerSelection,
  },
  data() {
    return {
      playersData: playersData,
      selection: [],
    };
  },
  methods: {
    addPlayerToSelection(player) {
      this.selection.push(player);
    },
  },
};
</script>

<style scoped>
</style>