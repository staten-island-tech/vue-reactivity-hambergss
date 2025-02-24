<template>
  <div>
    <header class="bg-dark-navy-blue text-white p-6 text-center flex justify-center items-center">
      <h1 class="text-3xl font-bold">Welcome to Switch Store!</h1>
    </header>

    <div class="flex mt-6">
      <div class="w-3/4 p-6 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <SwitchCards v-for="item in switches" :key="item.name" :switchItem="item">
          <button
            class="btn btn-primary bg-green-600 hover:bg-green-700 mt-4 rounded-lg shadow-sm outline outline-2 outline-black"
            @click="addToCart(item)"
          >
            Add to Cart
          </button>
        </SwitchCards>
      </div>
    </div>

    <div class="w-1/4 h-screen bg-gray-100 p-6 fixed right-0 top-0 overflow-y-auto">
      <h2 class="text-2xl font-semibold mb-4 text-dark-navy">Shopping Cart</h2>
      <div v-for="item in cart" :key="item.name" class="bg-white p-4 rounded-xl mb-4 shadow-sm">
        <p class="text-dark-navy">
          {{ item.name }} - ${{ item.price }} x {{ quantityFinder(item) }}
        </p>
        <button
          class="bg-red-600 text-white px-4 py-2 rounded-lg mt-2 hover:bg-red-700"
          @click="removeFromCart(item)"
        >
          Remove
        </button>
      </div>
      <div class="mt-6 text-lg font-semibold text-dark-navy">
        Total: ${{ totalPrice.toFixed(2) }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import SwitchCards from '@/components/SwitchCards.vue'

const switches = ref([
  { manufacturer: 'Gateron', name: 'Gateron Red', type: 'linear', sound: 'creamy', price: 1.99 },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Milky Yellow Pro (KS-3)',
    type: 'linear',
    sound: 'creamy',
    price: 2.49,
  },
  { manufacturer: 'HMX', name: 'HMX Poro', type: 'linear', sound: 'thocky', price: 4.99 },
  { manufacturer: 'KTT', name: 'KTT Strawberry', type: 'linear', sound: 'creamy', price: 3.49 },
  {
    manufacturer: 'Wuque Studios',
    name: 'WS Morandi',
    type: 'linear',
    sound: 'creamy',
    price: 5.49,
  },
  {
    manufacturer: 'Akko',
    name: 'V3 Cream Yellow Pro',
    type: 'linear',
    sound: 'creamy',
    price: 2.99,
  },
  { manufacturer: 'Gateron', name: 'Brown', type: 'tactile', sound: 'thocky', price: 2.19 },
  { manufacturer: 'Akko', name: 'Penguin', type: 'tactile', sound: 'thocky', price: 3.99 },
  { manufacturer: 'KTT', name: 'Lemon', type: 'tactile', sound: 'thocky', price: 2.79 },
  { manufacturer: 'Invyr', name: 'Holy Panda', type: 'tactile', sound: 'thocky', price: 5.99 },
  {
    manufacturer: 'Akko',
    name: 'V3 Creamy Purple Pro',
    type: 'tactile',
    sound: 'thocky',
    price: 3.29,
  },
  { manufacturer: 'Gateron', name: 'Blue', type: 'clicky', sound: 'clicky', price: 1.89 },
  { manufacturer: 'Gateron', name: 'Melodic', type: 'clicky', sound: 'clicky', price: 2.29 },
  { manufacturer: 'Akko', name: 'Creamy Cyan', type: 'clicky', sound: 'clicky', price: 2.59 },
  {
    manufacturer: 'Wuque Studios',
    name: 'Clicky Switch',
    type: 'clicky',
    sound: 'clicky',
    price: 4.49,
  },
  { manufacturer: 'Gateron', name: 'Silent Red', type: 'linear', sound: 'silent', price: 2.99 },
  { manufacturer: 'Gateron', name: 'Silent Brown', type: 'tactile', sound: 'silent', price: 3.19 },
  { manufacturer: 'Akko', name: 'Silent Red', type: 'linear', sound: 'silent', price: 2.79 },
  { manufacturer: 'Akko', name: 'Silent Brown', type: 'tactile', sound: 'silent', price: 3.49 },
  { manufacturer: 'HMX', name: 'HMX Cheese', type: 'linear', sound: 'clacky', price: 4.79 },
  { manufacturer: 'HMX', name: 'HMX Xinhai', type: 'linear', sound: 'clacky', price: 4.29 },
  { manufacturer: 'Gateron', name: 'Gateron Quinn', type: 'tactile', sound: 'clacky', price: 3.99 },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Baby Kangaroo (V2)',
    type: 'tactile',
    sound: 'clacky',
    price: 3.69,
  },
  { manufacturer: 'HMX', name: 'HMX Swift', type: 'linear', sound: 'clacky', price: 4.89 },
  { manufacturer: 'HMX', name: 'HMX Deep Navy', type: 'linear', sound: 'clacky', price: 4.59 },
  { manufacturer: 'HMX', name: 'HMX Macchiato', type: 'linear', sound: 'clacky', price: 5.29 },
  { manufacturer: 'HMX', name: 'HMX Sunset Gleam', type: 'linear', sound: 'clacky', price: 4.99 },
])

const cart = ref([])

const addToCart = (switchItem) => {
  const existingItem = cart.value.find((item) => item.name === switchItem.name) //finds if the item is already in the shoppin cart
  if (existingItem) {
    existingItem.quantity += 1
  } else {
    cart.value.push({
      name: switchItem.name,
      type: switchItem.type,
      price: switchItem.price,
      quantity: 1,
    })
  }
}

const removeFromCart = (item) => {
  const index = cart.value.findIndex((cartItem) => cartItem.name === item.name) //finds the index of the item in the cart
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
  return cartItem ? cartItem.quantity : 0 //returns the items quantity if found or 0 if not
}

const totalPrice = computed(() => {
  return cart.value.reduce((total, cartItem) => total + cartItem.price * cartItem.quantity, 0)
})
</script>

<style scoped>
.text-dark-navy {
  color: #1e3a8a;
}

body {
  background-color: #f7fafc;
  font-family: 'Inter', sans-serif;
  color: #2d3748;
}
</style>
