<script>
export default {
  name: 'FoodComponent',
  props: {
    name: {
      type: String,
      required: true
    },
    price: {
      type: Number,
      required: true
    },
    description: {
      type: String,
      default: ""
    }
  }
}
</script>

<template>
  <div>
    <h1 class="name">{{ name }}</h1>
    <h2 class="price">${{ price }}</h2>

    <p v-if="description != ''" class="description">
      {{ description }}
    </p>

  </div>
</template>

<style>
/* Aquí puedes agregar estilos si lo necesitas */
</style>
