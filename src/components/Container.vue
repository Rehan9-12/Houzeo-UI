<template>
  <div class="box">
    <Mapview />
    <Listingview />
    <div class="map-btn">
      Map
      <img src="/src/assets/icons/map.svg" alt="Map Icon" />
    </div>
  </div>
</template>

<script setup>
import Mapview from './Mapview.vue';
import Listingview from './Listingview.vue';
</script>

<style>
.box {
  display: flex;
  width: 100%;
  overflow: hidden;
}

.map-btn {
  position: fixed;               /* Stick to viewport */
  bottom: 2rem;                  /* Distance from bottom */
  left: 50%;                     /* Center horizontally */
  transform: translateX(-50%);   /* Perfect horizontal centering */
  background-color: #0d61a8;
  color: white;
  font-weight: 400;
  font-size: 1.3rem;
  display: none;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1.5rem;
  border-radius: 2rem;
  z-index: 1000;                 /* Ensure it appears above other elements */
}

@media (max-width: 1000px) {
  .map-btn {
    display: flex;
  }
}
</style>
