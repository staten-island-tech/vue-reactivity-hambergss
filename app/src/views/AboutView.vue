<template>
  <div>
    <form @submit.prevent="" action="submit">
      <label for="username">Username</label>
      <input type="text" v-model="user.username" />
      <label for="password"></label>
      <input type="password" v-model="user.password" />
      <button>Submit</button>
    </form>
    <h2 v-if="loggedIn">Hello Peter</h2>
    <h2 v-else>Please Login</h2>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
const 

</script>

<style scoped></style>
