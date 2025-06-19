<template>
  <div class="map-view">
      <iframe class="map" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d440949.9630487902!2d-98.06263121825191!3d30.2962938561678!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8644b599a0cc032f%3A0x5d9b464bd469d57a!2sAustin%2C%20TX%2C%20USA!5e0!3m2!1sen!2sin!4v1750192390262!5m2!1sen!2sin" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
  </div>
</template>

<script>
export default {
  name: 'MapView'
}
</script>

<style scoped>
.map-view {
  flex: 1;
  min-width: 400px;
  width: 50%;
  background-color: #e5e7eb;
  display: flex;
  align-items: center;
  justify-content: center;
  border-right: 1px solid #ccc;
}
.map{
  width: 100%;
  height: 100%;
}


@media (max-width:1000px) {
  .map-view{
    display: none;
  }
}



</style>
