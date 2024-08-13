<script>
import jugos from '@/assets/jugos.jpeg'
import lonche from '@/assets/lonche.jpeg'
import pan from '@/assets/pan.jpeg'
import panini from '@/assets/panini.jpeg'

export default {
  name: 'Menu-display',
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      model: 0,  // Controla la diapositiva actual del carrusel
      items: [
        { src: jugos, id: 1, title: 'Jugos', description: 'Jugos naturales' },
        { src: lonche, id: 2, title: 'Lonches', description: 'Lonches de jamón, queso, etc.' },
        { src: pan, id: 3, title: 'Pan', description: 'Pan dulce y salado' },
        { src: panini, id: 4, title: 'Panini', description: 'Panini de jamón, queso, etc.' },
      ],
    }
  }
}
</script>

<template>
  <div class="carrousel-container">
    <v-carousel v-model="model" class="carrousel">
      <v-carousel-item v-for="(item, i) in items" :key="item.id" :value="i">
        <v-sheet tile>
          <div class="carrousel-image">
            <img :src="item.src" :alt="item.title">
          </div>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
    <div tile class="carrousel-title">
        <div class="text-h2">{{ items[model].title }}</div>
        <div class="text-h3">{{ items[model].description }}</div>
    </div>
  </div>
</template>

<style scoped>
.text-h3{
  font-size: 1.5rem;
  font-weight: 500;
  margin: 1rem 0;
  text-overflow: ellipsis;
  overflow: hidden;
}

.text-h2 {
  font-size: 2rem;
  font-weight: 700;
  margin: 1rem 0;
}

.carrousel-title{
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #B08969;
  text-align: center;
  color: white;
  font-size: 2rem;
  width: 700px;
  flex-direction: column;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  margin: 0 1rem;
  height: 80%;
}

.carrousel-container {
  display: grid;
  place-items: center;
  margin: 2rem 0;
  grid-template-columns: 1fr 1fr;
}

.carrousel {
  margin: 2rem auto;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

.carrousel-image {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 400px;
}

@media (max-width: 1300px) {
  .carrousel-container {
    grid-template-columns: 1fr;
    margin: 0;
  }
}
</style>
