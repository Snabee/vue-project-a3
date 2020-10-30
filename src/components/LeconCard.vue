<template>
  <div class="max-w-sm rounded overflow-hidden shadow-lg">
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
      <base-button text="Sélectionner" @click="addToCurrent"></base-button>
    </div>
    <div class="px-6 pt-4 pb-2">
      <span
        class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
        >{{ lecon.category }}</span
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "lecon-card",
  props: ["lecon"],
  methods: {
    addToCurrent() {
      this.$emit("add-lecon", this.lecon);
    },
  },
};
</script>

<style scoped>
</style>