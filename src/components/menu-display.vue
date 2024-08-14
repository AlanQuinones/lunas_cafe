<script>
import jugos from '@/assets/jugos.jpeg'
import lonche from '@/assets/lonche.jpeg'
import pan from '@/assets/pan.jpeg'
import panini from '@/assets/panini.jpeg'
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiHeart } from '@mdi/js';

export default {
  name: 'Menu-display',
  components: {
    SvgIcon
  },
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
      heart: mdiHeart,
    }
  }
}
</script>

<template>
  <h2 class="title-section">
    <svg-icon type="mdi" :path="heart" class="heart-icon"></svg-icon>
      Lo mas pedido
    <svg-icon type="mdi" :path="heart" class="heart-icon"></svg-icon>
  </h2>
  <div class="carrousel-container">
    <v-carousel v-model="model" class="carrousel">
      <v-carousel-item v-for="(item, i) in items" :key="item.id" :value="i" :src="item.src" cover class="carrousel-image">
      </v-carousel-item>
    </v-carousel>
    <div tile class="carrousel-title">
      <div class="text-h2">{{ items[model].title }}</div>
      <div class="text-h3">{{ items[model].description }}</div>
    </div>
  </div>
</template>

<style scoped>
.text-h2 {
  font-size: 2rem;
  font-weight: 700;
  margin: 0;
}

.text-h3 {
  font-size: 1.5rem;
  font-weight: 400;
  margin: 0;
}

.carrousel-title {
  margin: 2rem;
  text-align: center;
  height: 500px;
  width: 100%;
  background-color: #B08969;
  border-radius: 10px;
  font-family: 'quicksand', sans-serif;
  color: #EDE0D4;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.carrousel-container {
  display: flex;
  align-items: center;
}

.carrousel {
  max-width: 700px;
  border-radius: 10px;
  margin: 2rem;
}

.title-section {
  text-align: center;
  font-size: 1.8rem;
  margin: 1rem 2rem -1rem 2rem;
  font-family: 'quicksand', sans-serif;
  color: #2C2C30;
}

.heart-icon {
  color: #2C2D30;
}

@media (max-width: 900px) {
  .carrousel-container {
    flex-direction: column;
  }
  .carrousel-title {
    padding: 10px;
    margin: 0;
    border-radius: 0;
    position: relative;
    width: 100%;
    height: 200px;
    background: rgb(0,0,0);
    background: linear-gradient(180deg, rgba(0,0,0,1) 4%, rgba(0,0,0,0) 100%);
    color: white;
  }
  .carrousel {
    position: absolute;
    max-width: 100%;
    margin: 0;
    border-radius: 0;
  }

  .title-section {
    font-size: 1.5rem;
    margin: 1rem 0;
  }

  .text-h2 {
    margin-top: 1rem;
    font-size: 10px;
  }

  .text-h3 {
    font-size: 1rem;
  }
}
</style>
