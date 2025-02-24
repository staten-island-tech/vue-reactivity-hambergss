<template>
  <div class="space-x-4">
    <button @click="filterSwitches('all')" class="bg-gray-200 py-2 px-4 rounded hover:bg-gray-300">
      All
    </button>
    <button
      @click="filterSwitches('linear')"
      class="bg-gray-200 py-2 px-4 rounded hover:bg-gray-300"
    >
      Linear
    </button>
    <button
      @click="filterSwitches('tactile')"
      class="bg-gray-200 py-2 px-4 rounded hover:bg-gray-300"
    >
      Tactile
    </button>
    <button
      @click="filterSwitches('clicky')"
      class="bg-gray-200 py-2 px-4 rounded hover:bg-gray-300"
    >
      Clicky
    </button>
  </div>
</template>

<script setup>
defineProps({
  filterSwitches: Function,
})
</script>
