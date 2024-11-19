<template>
  <p>Compteur : {{ count }}</p>
  <div v-if="count > 6">Congrats vous avez cliqué plus de 6 fois</div>
  <div v-else>Vous avez cliqué moins de 6 fois</div>

  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
</template>

<script setup>
import { ref } from "vue";
const count = ref(0);
const increment = (event) => count.value++;
const decrement = () => count.value--;
</script>

<style>
h1 {
  color: red;
}
</style>
