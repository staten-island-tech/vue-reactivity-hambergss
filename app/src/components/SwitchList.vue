<template>
    <div>
        <h2>Switches</h2>
        <SwitchCards v-for="switche in switches" :key="switche.id" :switche="switche" :addtoCart="props.addtoCart"/>
    </div>
</template>

<script setup>
import { ref, defineProps } from 'vue';
import SwitchCards from './SwitchCards.vue';

const props = defineProps(['addToCart'])
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
</script>

<style scoped>

</style>