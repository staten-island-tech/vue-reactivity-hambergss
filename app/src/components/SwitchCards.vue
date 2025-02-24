<template>
  <div class="bg-white p-4 rounded-xl shadow-md hover:shadow-lg transition-all">
    <img
      :src="switchItem.imageUrl"
      :alt="switchItem.alt"
      class="w-full h-48 object-cover rounded-lg"
    />
    <h3 class="card-title text-lg font-bold text-dark-navy">{{ switchItem.name }}</h3>
    <p class="text-dark-navy mt-1">{{ switchItem.description }}</p>
    <p class="text-lg font-semibold text-dark-navy mt-2">${{ switchItem.price }}</p>
    <slot></slot>
  </div>
</template>

<script setup>
defineProps({
  switchItem: Object,
  addToCart: Function,
})
</script>

<style scoped>
.text-dark-navy {
  color: #1e3a8a;
}
</style>
