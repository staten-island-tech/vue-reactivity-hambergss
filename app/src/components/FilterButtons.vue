<template>
  <div class="flex justify-center mt-10">
    <div class="flex space-x-2 p-4 bg-white shadow-md rounded-md">
      <button
        @click="filterSwitches('all')"
        class="bg-[#28d6b0] text-[#15162d] py-2 px-4 rounded-md hover:bg-[#2bb698] transition"
      >
        All
      </button>
      <button
        @click="filterSwitches('linear')"
        class="bg-[#28d6b0] text-[#15162d] py-2 px-4 rounded-md hover:bg-[#2bb698] transition"
      >
        Linear
      </button>
      <button
        @click="filterSwitches('tactile')"
        class="bg-[#28d6b0] text-[#15162d] py-2 px-4 rounded-md hover:bg-[#2bb698] transition"
      >
        Tactile
      </button>
      <button
        @click="filterSwitches('clicky')"
        class="bg-[#28d6b0] text-[#15162d] py-2 px-4 rounded-md hover:bg-[#2bb698] transition"
      >
        Clicky
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  filterSwitches: Function,
})
</script>
