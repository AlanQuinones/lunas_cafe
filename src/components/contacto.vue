<script>
  export default {
    data: () => ({
      icons: [
        {
          icon: 'mdi-instagram',
          link: 'https://www.instagram.com/lunasoficcial23/',
        },
      ],
    }),
  }
</script>
<template>
  <v-footer class="flex flex-column social-media-container">
    <div>
      <strong>Encuentranos en nuestras redes sociales</strong>
      <v-spacer></v-spacer>
      <v-btn
        v-for="icon in icons"
        :key="icon"
        :icon="icon.icon"
        size="large"
        variant="plain"
        :href="icon.link"
        target="_blank"
        class="social-media"
      ></v-btn>
    </div>
      {{ new Date().getFullYear() }} — Lunas Cafe
  </v-footer>
</template>
<style>
.social-media {
  margin: 0 0.5rem;
}

.social-media-container {
  background-color: #2C2C30;
  color: white;
  padding: 1rem;
  text-align: center;
}
</style>
