<template>
  <button
    class="bg-white my-3 hover:bg-gray-300 text-black font-bold py-2 px-4 rounded transition duration-200 ease-in-out">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "base-button",
  props: ["text"],
};
</script>

<style>
</style>