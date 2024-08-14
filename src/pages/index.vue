<template>
  <Navbar titlePage="Luna's Cafe" />
  <MenuDisplay />
  <v-divider inset class="division-bar"></v-divider>
</template>
<script setup>
import Navbar from '@/components/navbar.vue';
import MenuDisplay from '@/components/menu-display.vue';
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
