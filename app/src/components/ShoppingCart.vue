<template>
  <div class="w-1/4 h-screen bg-[#ead0c8] p-6 fixed right-0 top-0 overflow-y-auto">
    <h2 class="text-2xl font-semibold mb-4 text-[#15162d]">Shopping Cart</h2>

    <div v-for="item in cart" :key="item.name" class="bg-[#f2e3de] p-4 rounded-xl mb-6 shadow-sm">
      <p class="text-[#15162d]">{{ item.name }} - ${{ item.price }} x {{ quantityFinder(item) }}</p>
      <button
        class="bg-red-600 text-white px-4 py-2 rounded-lg mt-2 hover:bg-red-700"
        @click="removeFromCart(item)">
        Remove
      </button>
    </div>

    <div class="mt-6 text-lg font-semibold text-[#15162d]">Total: ${{ totalPrice.toFixed(2) }}</div>
  </div>
</template>

<script setup>
defineProps({
  cart: Array,
  quantityFinder: Function,
  removeFromCart: Function,
  totalPrice: Number,
})
</script>
