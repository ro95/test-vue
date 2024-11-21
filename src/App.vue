<template>
  <p :style="{ active: count > 6 }">Compteur : {{ count }}</p>
  <div v-if="count > 6">Congrats vous avez cliqué plus de 6 fois</div>
  <div v-else>Vous avez cliqué moins de 6 fois</div>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <button @click="SortMovie">Réorganiser</button>
  <ul>
    <li v-for="movie in movies" :key="movie">
      {{ movie }} <button @click="deleteMovie(movie)">Delete</button>
    </li>
  </ul>
</template>

<script setup>
import { ref } from "vue";
const count = ref(0);
const movies = ref([
  "The Shawshank Redemption",
  "The Godfather",
  "The Dark Knight",
]);

const increment = (event) => count.value++;
const decrement = () => count.value--;

const deleteMovie = (movie) => {
  movies.value = movies.value.filter((m) => m !== movie);
};
const SortMovie = () => {
  movies.value.sort((a, b) => (a > b ? 1 : -1));
};
</script>
