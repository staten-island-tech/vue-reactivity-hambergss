<template>
  <div>
    <h2 class="mx-auto justify-self-center">Genshin Popup Event</h2>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
const itemsArray = [
  {
    category: 'Keychains',
    items: [
      'Paimon Keychain',
      'Klee Keychain',
      'Diluc Keychain',
      'Zhongli Keychain',
      'Venti Keychain',
      'Raiden Shogun Keychain',
      'Xiao Keychain',
      'Barbara Keychain',
    ],
  },
  {
    category: 'Plushies',
    items: [
      'Paimon Plushie', 
      'Klee Plushie', 
      'Qiqi Plushie', 
      'Amber Plushie', 
      'Barbara Plushie', 
    ],
  },
  {
    category: 'Pins',
    items: [
      'Paimon Pin', 
      'Klee Pin', 
      'Diluc Pin', 
      'Zhongli Pin', 
      'Venti Pin', 
      'Raiden Shogun Pin', 
    ],
  },
  {
    category: 'T-shirts',
    items: [
      'Klee T-shirt',
      'Diluc T-shirt',
      'Zhongli T-shirt',
      'Venti T-shirt',
      'Raiden Shogun T-shirt',
    ],
  },
  {
    category: 'Phone Cases',
    items: [
      'Paimon Phone Case',
      'Klee Phone Case',
      'Diluc Phone Case',
      'Zhongli Phone Case',
      'Venti Phone Case',
    ],
  },
]


</script>

<style scoped></style>
