<template>
  <div>
    <h2 class="mx-auto justify-self-center">Genshin Popup Event</h2>
    <div>
      <button @click="filterByManufacturer('Gateron')">Filter by Gateron</button>
      <button @click="filterByManufacturer('Akko')">Filter by Akko</button>
      <button @click="filterByManufacturer('HMX')">Filter by HMX</button>
      <button @click="clearFilter">Clear Filter</button>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
const switches = [
  {
    manufacturer: 'Gateron',
    name: 'Red',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'Gateron',
    name: 'Milky Yellow Pro (KS-3)',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'HMX',
    name: 'Xinhai',
    type: 'linear',
    sound: 'thocky',
  },
  {
    manufacturer: 'HMX',
    name: 'Poro',
    type: 'linear',
    sound: 'thocky',
  },
  {
    manufacturer: 'KTT',
    name: 'Strawberry',
    type: 'linear',
    sound: 'creamy',
  },
  {
    manufacturer: 'Akko',
    name: 'Linear 3051',
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
    manufacturer: 'Gateron',
    name: 'Tactile',
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
    manufacturer: 'Holy Panda',
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
    type: 'silent',
    sound: 'silent',
  },
  {
    manufacturer: 'Gateron',
    name: 'Silent Brown',
    type: 'silent',
    sound: 'silent',
  },
  {
    manufacturer: 'Akko',
    name: 'Silent Red',
    type: 'silent',
    sound: 'silent',
  },
  {
    manufacturer: 'Akko',
    name: 'Silent Brown',
    type: 'silent',
    sound: 'silent',
  },
]

const switchesList = document.getElementById('switches-list')


</script>

<style scoped></style>
