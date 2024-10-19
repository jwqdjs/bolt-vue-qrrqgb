<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="app">
    <header>
      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </header>

    <RouterView />

    <footer>
      <nav class="bottom-nav">
        <RouterLink to="/shopping">Shopping</RouterLink>
        <RouterLink to="/life">Life</RouterLink>
        <RouterLink to="/study">Study</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </footer>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  padding: 20px;
}

header nav a {
  font-weight: bold;
  color: #2c3e50;
}

header nav a.router-link-exact-active {
  color: #42b983;
}

.bottom-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: #f8f8f8;
  display: flex;
  justify-content: space-around;
  padding: 10px 0;
  box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
}

.bottom-nav a {
  color: #2c3e50;
  text-decoration: none;
  font-size: 0.9rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.bottom-nav a.router-link-active {
  color: #42b983;
}

.bottom-nav a::before {
  content: '';
  font-size: 1.5rem;
  margin-bottom: 5px;
}

.bottom-nav a[href="/shopping"]::before { content: '🛒'; }
.bottom-nav a[href="/life"]::before { content: '🌿'; }
.bottom-nav a[href="/study"]::before { content: '📚'; }
.bottom-nav a[href="/about"]::before { content: 'ℹ️'; }

/* Add some bottom padding to the main content to prevent overlap with the navigation bar */
main {
  flex: 1;
  padding-bottom: 60px; /* Adjust this value based on the height of your bottom nav */
}
</style>