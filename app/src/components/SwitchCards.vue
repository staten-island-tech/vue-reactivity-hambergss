<template>
  <div class="bg-[#f2ecea] p-4 rounded-xl shadow-md hover:shadow-lg transition-all h-160 flex flex-col">
    <img
      :src="switchItem.imageUrl"
      :alt="switchItem.alt"
      class="w-full h-120 object-cover rounded-lg"
    />
    <h3 class="card-title text-lg font-bold text-[#15162d]">{{ switchItem.name }}</h3>
    <h2 class="text-[#15162d] mt-1">{{ switchItem.manufacturer }}</h2>
    <p class="text-[#15162d] mt-1">{{ switchItem.description }}</p>
    <p class="text-lg font-semibold text-[#15162d] mt-2">${{ switchItem.price }}</p>
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
