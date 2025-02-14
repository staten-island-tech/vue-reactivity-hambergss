<template>
  <div>
    <h2 class="mx-auto justify-self-center">Genshin Popup Event</h2>
    <button @click="filterSwitches('Gateron')">Gateron</button>
    <button @click="filterSwitches('Akko')">Akko</button>
    <button @click="filterSwitches('Wuque Studios')">Wuque Studios</button>
    <button @click="filterSwitches('HMX')">HMX</button>
    <button @click="filterSwitches('KTT')">KTT</button>
    <button @click="filterByType('linear')">Linear</button>
    <button @click="filterByType('tactile')">Tactile</button>
    <button @click="filterByType('clicky')">Clicky</button>
    <button @click="filterByType('silent')">Silent</button>
    <ul>
      <li v-for="switche in filteredSwitches" :key="switche.name">
        {{ switche.name }} - {{ switche.manufacturer }} - {{ switche.type }} - {{ switche.sound }}
      </li>
    </ul>
    <div class="card">
      <h1>{{ switche.name }}</h1>
      <p>{{ switche.manufacturer }} - {{ switche.type }} - {{ switche.sound }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { defineProps } from 'vue'

const filteredSwitches = ref(switches)

function filterSwitches(manufacturer) {
  filteredSwitches.value = switches.filter((switche) => switche.manufacturer === manufacturer)
}

function filterByType(type) {
  filteredSwitches.value = switches.filter((switche) => switche.type === type)
}

defineProps({
  switche: Object,
})
</script>

<style scoped>
.card {
  padding: 10px;
  border: 1px solid #ccc;
  margin: 10px;
}
</style>
