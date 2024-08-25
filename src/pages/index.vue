<template>
  <Navbar titlePage="Luna's Cafe" />
  <h2 id="inicio"></h2>
  <MenuDisplay />
  <h2 id="menu"></h2>
  <Menu />
  <h2 id="Horario"></h2>
  <Horario />
  <h2 id="ubicacion"></h2>
  <Ubicacion />
  <h2 id="contacto"></h2>
  <Contacto />
</template>
<script setup>
import Navbar from '@/components/navbar.vue';
import MenuDisplay from '@/components/menu-display.vue';
import Menu from '@/components/menu.vue';
import Horario from '@/components/horario.vue';
import Ubicacion from '@/components/ubicacion.vue';
</script>
<style>
.division-bar {
  border: 1px solid black;
  margin-right: 4rem;
}

@media (max-width: 900px) {
  .division-bar {
    display: none;
  }
}

</style>
