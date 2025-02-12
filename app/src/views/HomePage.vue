<template>
  <div class="min-h-screen bg-gray-100 p-6">
    <!-- Header Section -->
    <header class="text-center mb-6">
      <h1 class="text-4xl font-bold text-gray-800">Keyboard Switch Store</h1>
      <button
        @click="addSwitch"
        class="mt-4 bg-blue-500 text-white px-6 py-3 rounded-lg shadow-lg hover:bg-blue-600 focus:outline-none"
      >
        Add New Switch
      </button>
    </header>

    <!-- Switch Cards Section -->
    <section class="flex flex-wrap justify-center gap-6">
      <SwitchCards v-for="switche in switches" :key="switche.name" :switche="switche" />
    </section>

    <!-- Footer Section -->
    <footer class="text-center mt-8">
      <p class="text-gray-600">Switches</p>
    </footer>
  </div>
</template>

<script setup>
import { reactive } from 'vue'
import SwitchCards from './components/SwitchCards.vue'

// Reactive data array for the switches
const switches = reactive([
  {
    manufacturer: 'Gateron',
    name: 'Gateron Red',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Milky Yellow Pro (KS-3)',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Poro',
    type: 'linear',
    sound: 'thocky',
  },
  {
    manufacturer: 'KTT',
    name: ' KTT Strawberry',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'Wuque Studios',
    name: 'WS Morandi',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'Akko',
    name: 'V3 Cream Yellow Pro',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'Gateron',
    name: 'Brown',
    type: 'tactile',
    sound: 'thocky',
  },
  {
    manufacturer: 'Akko',
    name: 'Penguin',
    type: 'tactile',
    sound: 'thocky',
  },
  {
    manufacturer: 'KTT',
    name: 'Lemon',
    type: 'tactile',
    sound: 'thocky',
  },
  {
    manufacturer: 'Invyr',
    name: 'Holy Panda',
    type: 'tactile',
    sound: 'thocky',
  },
  {
    manufacturer: 'Akko',
    name: 'V3 Creamy Purple Pro',
    type: 'tactile',
    sound: 'thocky',
  },

  {
    manufacturer: 'Gateron',
    name: 'Blue',
    type: 'clicky',
    sound: 'clicky',
  },
  {
    manufacturer: 'Gateron',
    name: 'Melodic',
    type: 'clicky',
    sound: 'clicky',
  },
  {
    manufacturer: 'Akko',
    name: 'Creamy Cyan',
    type: 'clicky',
    sound: 'clicky',
  },
  {
    manufacturer: 'Wuque Studios',
    name: 'Clicky Switch',
    type: 'clicky',
    sound: 'clicky',
  },
  {
    manufacturer: 'Gateron',
    name: 'Silent Red',
    type: 'linear',
    sound: 'silent',
  },
  {
    manufacturer: 'Gateron',
    name: 'Silent Brown',
    type: 'tactile',
    sound: 'silent',
  },
  {
    manufacturer: 'Akko',
    name: 'Silent Red',
    type: 'linear',
    sound: 'silent',
  },
  {
    manufacturer: 'Akko',
    name: 'Silent Brown',
    type: 'tactile',
    sound: 'silent',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Cheese',
    type: 'linear',
    sound: 'clacky',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Xinhai',
    type: 'linear',
    sound: 'clacky',
  },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Quinn',
    type: 'tactile',
    sound: 'clacky',
  },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Baby Kangaroo (V2)',
    type: 'tactile',
    sound: 'clacky',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Swift',
    type: 'linear',
    sound: 'clacky',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Deep Navy',
    type: 'linear',
    sound: 'clacky',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Macchiato',
    type: 'linear',
    sound: 'clacky',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Sunset Gleam',
    type: 'linear',
    sound: 'clacky',
  },
])

// Function to add a new switch
function addSwitch() {
  switches.push({
    name: `Switch ${Date.now()}`,
    manufacturer: 'Unknown',
    type: 'linear',
    sound: 'creamy',
  })
}
</script>

<style scoped>
/* TailwindCSS already provides utility classes, so custom CSS is minimal */
</style>
