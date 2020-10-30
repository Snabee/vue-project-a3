<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Mes cours</h1>

    <div v-if="current.length == 0">
      <p>Veuillez sélectionner un cours auparavant.</p>
    </div>
    <div v-else>
      <div
        v-for="lecon in current"
        :key="lecon.name"
        class="rounded overflow-hidden shadow-lg my-4 p-2"
      >
        <div>
          <img
            class="w-full"
            src="https://picsum.photos/640/360"
            alt="Sunset in the mountains"
          />
          <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{{ lecon.name }}</div>
            <p class="text-gray-700 text-base">
              {{ lecon.description }}
            </p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <span
              class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
              >{{ lecon.category }}</span
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "current-list",
  props: ["current"],
  computed: {
    total() {
      var total = this.current.reduce(function (previousValue, currentValue) {
        return previousValue.number + currentValue.number;
      });

      return total;
    },
  },
};
</script>

<style>
</style>