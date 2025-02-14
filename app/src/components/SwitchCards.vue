<template>
  <div class="bg-white p-6 rounded-lg shadow-lg w-72 hover:shadow-xl transition-all">
    <h2 class="text-2xl font-bold text-gray-800 mb-2">{{ switche.name }}</h2>
    <p class="text-sm text-gray-600 mb-1">
      <strong>Manufacturer:</strong> {{ switche.manufacturer }}
    </p>
    <p class="text-sm text-gray-600 mb-1"><strong>Type:</strong> {{ switche.type }}</p>
    <p class="text-sm text-gray-600 mb-1"><strong>Sound:</strong> {{ switche.sound }}</p>
    <p>Price: ${{ switche.price }}</p>
    <button @click="props.addtoCart(switche)">Add to Cart</button>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps(['switche', 'addtoCart'])
</script>

<style scoped></style>
