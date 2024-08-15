<template>
  <v-app>
    <v-main class="main">
      <router-view />
    </v-main>
  </v-app>
</template>

<script setup>
  //
</script>
<style>
.main {
  font-family: 'quicksand', sans-serif;
  font-size: 16px;
  color: #333;
  /* background-color: #E6CCB2; */
  background-image: url('https://i.pinimg.com/564x/63/f6/b5/63f6b5bb72254411275489f7265b2f75.jpg');
  background-repeat: repeat; /* Repetir la imagen */
  background-size: cover; /* Rellenar toda la pantalla */
  background-position: center; 
}

html {
  z-index: -1;
  scroll-behavior: smooth;
}
</style>
