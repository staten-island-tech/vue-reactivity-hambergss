<template>
  <div>
    <h2>Shopping Cart</h2>
    <ul v-if="cart.length > 0">
      <li v-for="item in cart" :key="item.id">
        {{ item.name }} - ${{ item.price }}
        <button @click="removeFromCart(item)">Remove</button>
      </li>
    </ul>
    <p v-else>The Cart is Empty</p>
    <h3>Total Price: ${{ totalPrice }}</h3>
  </div>
</template>

<script setup>
import { defineProps, computed } from 'vue'
const props = defineProps(['cart'])

const removeFromCart = (switche) => {
  props.cart.splice(props.cart.indexOf(switche), 1)
}
const totalPrice = computed(() => {
  return props.cart.reduce((sum, item) => sum + item.price, 0)
})
</script>

<style scoped></style>
