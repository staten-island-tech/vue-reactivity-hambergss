<template>
  <div>
    <FilterButtons v-for="switche in switches" :key="switche.name" />
  </div>
</template>

<script setup>
import FilterButtons from './components/FilterButtons.vue'
switches.forEach((switche) =>
  document
    .querySelector('.container')
    .insertAdjacentElement(`<div className="card"><h1>${switche.name}</h1></div>`),
)
</script>

<style scoped></style>
