<template>
  <div
    class="card w-64 bg-white shadow-xl p-4 rounded-xl hover:shadow-2xl transition-shadow mt-3vh"
  >
    <figure class="w-full h-40 flex justify-center items-center">
      <img :src="item.imageUrl" :alt="item.alt" class="w-auto h-full object-cover rounded-lg" />
    </figure>
    <div class="card-body text-center">
      <h2 class="card-title text-lg font-bold text-dark-navy">{{ item.name }}</h2>
      <p class="text-dark-navy text-sm">{{ item.description }}</p>
      <p class="text-lg font-semibold text-dark-navy mt-2">${{ item.price }}</p>
      <p class="text-lg font-semibold text-dark-navy mt-2">Quantity: {{ number }}</p>
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
defineProps({
  cart: Array,
  removeFromCart: Function,
})
</script>

<style scoped>
.text-dark-navy {
  color: #1e3a8a;
}
</style>
