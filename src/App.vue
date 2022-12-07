<script setup lang="ts">

import { ref } from 'vue';

const loggedIn = ref(false);
const username = ref<string>();
const password = ref<string>();
const error = ref<string | null>();

const login = () => {
  if (username.value === 'admin' && password.value === 'admin') {
    loggedIn.value = true;
  } else {
    error.value = "Invalid username or password"
  }
}

</script>

<template>
  <div v-if="loggedIn">
    <h1>You are logged in!</h1>
    <button @click="loggedIn = false">Logout</button>
  </div>
  <div v-else>
    <h1>Hello and welcome to the login page!</h1>
    <div>
      <label>
        Username
        <input type="email" v-model="username" />
      </label>
      <label>
        Password
        <input type="password" v-model="password" />
      </label>
      <button @click="login">Login</button>
    </div>
  </div>
</template>

<style scoped>

label {
  display: block;
}
</style>
