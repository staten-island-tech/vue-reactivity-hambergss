<template>
  <div class="w-1/4 h-screen bg-[#ead0c8] p-6 fixed right-0 top-0 overflow-y-auto">
    <h2 class="text-2xl font-semibold mb-4 text-[#15162d]">Shopping Cart</h2>
    <div v-for="item in cart" :key="item.name" class="bg-[#f2e3de] p-4 rounded-xl mb-6 shadow-sm">
      <p class="text-[#15162d]">{{ item.name }} - ${{ item.price }} x {{ quantityFinder(item) }}</p>
      <button
        class="bg-red-600 text-white px-4 py-2 rounded-lg mt-2 hover:bg-red-700"
        @click="removeFromCart(item)"
      >
        Remove
      </button>
    </div>
    <div class="mt-6 text-lg font-semibold text-[#15162d]">Total: ${{ totalPrice.toFixed(2) }}</div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const cart = ref([])

const addToCart = (switchItem) => {
  const existingItem = cart.value.find((item) => item.name === switchItem.name)
  if (existingItem) {
    existingItem.quantity += 1
  } else {
    cart.value.push({
      name: switchItem.name,
      price: switchItem.price,
      quantity: 1,
    })
  }
}

const removeFromCart = (item) => {
  const index = cart.value.findIndex((cartItem) => cartItem.name === item.name)
  if (index !== -1) {
    if (cart.value[index].quantity > 1) {
      cart.value[index].quantity -= 1
    } else {
      cart.value.splice(index, 1)
    }
  }
}

const quantityFinder = (item) => {
  const cartItem = cart.value.find((cartItem) => cartItem.name === item.name)
  return cartItem ? cartItem.quantity : 0
}

const totalPrice = computed(() => {
  return cart.value.reduce((total, cartItem) => total + cartItem.price * cartItem.quantity, 0)
})
</script>
