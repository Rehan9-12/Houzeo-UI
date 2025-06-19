<template>
  <header class="header">
    <img
      src="/assets/logo.webp"
      alt="Houzeo Logo"
      class="logo fade-in-up"
    />
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  height: auto;
  padding: 1rem 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  z-index: 50;
}

.logo {
  height: 32px;
}

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
