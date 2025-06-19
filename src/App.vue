<template>
  <div class="app-container">
    <Header />
    <Searchbar />
    <Container />
  </div>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';

const Header = defineAsyncComponent(() =>
  import('./components/Header.vue')
);
const Searchbar = defineAsyncComponent(() =>
  import('./components/Searchbar.vue')
);
const Container = defineAsyncComponent(() =>
  import('./components/Container.vue')
);
</script>

<style>
/* Reset base styles */
body,
html,
#app {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}

/* App container layout */
.app-container {
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  background-color: #f5f5f5;
}

/* Utility class for flex container */
.container {
  display: flex;
}

/* Fade-in animation */
.fade-in-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInUp 0.6s ease-out forwards;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
