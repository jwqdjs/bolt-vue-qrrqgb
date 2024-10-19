<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="home">
    <h1>Welcome to Our App</h1>
    <div class="shortcuts">
      <RouterLink v-for="route in ['shopping', 'life', 'study', 'about']" :key="route" :to="'/' + route" class="shortcut">
        <h2>{{ route.charAt(0).toUpperCase() + route.slice(1) }}</h2>
        <p>Explore our {{ route }} section</p>
      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 2rem;
}

.shortcuts {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
  max-width: 800px;
  width: 100%;
}

.shortcut {
  background-color: #f0f0f0;
  border-radius: 8px;
  padding: 1rem;
  text-align: center;
  text-decoration: none;
  color: inherit;
  transition: background-color 0.3s;
}

.shortcut:hover {
  background-color: #e0e0e0;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

p {
  font-size: 1rem;
  color: #666;
}
</style>