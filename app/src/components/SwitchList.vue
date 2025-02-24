<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
    <SwitchCards
      v-for="switchItem in switches"
      :key="switchItem.name"
      :switchItem="switchItem"
      :addToCart="addToCart"
    />
  </div>
</template>

<script setup>
import SwitchCards from './SwitchCards.vue'

defineProps({
  switches: Array,
  addToCart: Function,
})
</script>
