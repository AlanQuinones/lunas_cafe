<script>
export default {
  name: 'ScheduleComponent',
  props: {
    day: {
      type: String,
      required: true
    },
    time: {
      type: String,
      required: true
    },
  }
}
</script>

<template>
  <div>
    <h1 class="day">{{ day }}</h1>
    <h2 class="time">{{ time }}</h2>

  </div>
</template>

<style>
/* Aquí puedes agregar estilos si lo necesitas */
</style>
