<script>
import orangeCoffe from '@/assets/oraCoffe.jpeg'
import lonche from '@/assets/lonche.jpeg'
import pan from '@/assets/pan.jpeg'
import panini from '@/assets/panini.jpeg'
import mocha from '@/assets/mochaFrio.jpeg'
import galleta1 from '@/assets/galletaNutella.jpeg'
import galleta2 from '@/assets/GalletasLuna.jpeg'

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
        { src: orangeCoffe, id: 1, title: 'Cafe', description: 'Orange Coffe' },
        { src: mocha, id:2, title: 'Cafe frio', description: 'Mocha Frio'},
        { src: lonche, id: 3, title: 'Paninis', description: 'Panini Original' },
        { src: pan, id: 4, title: 'Panaderia', description: 'Pan dulce y salado' },
        { src: panini, id: 5, title: 'Panini', description: 'Panini Original' },
        { src: galleta1, id: 6, title: 'Galleta', description: 'GalletaNutella' },
        { src: galleta2, id: 6, title: 'Galletas', description: 'Galletas de chispas' },
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
    <v-carousel v-model="model" class="carrousel-phone" hide-delimiters>
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
  margin: 6rem 2rem -1rem 2rem;
  font-family: 'quicksand', sans-serif;
  color: #2C2C30;
}

.heart-icon {
  color: #2C2D30;
}

.carrousel-phone {
  display: none;
}

@media (max-width: 900px) {
  .carrousel-container {
    flex-direction: column;
    font-size: 1.5rem;
    margin: 3rem 0;
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
  .carrousel-phone {
    display: block;
    position: absolute;
    max-width: 100%;
    margin: 0;
    border-radius: 0;
  }

  .carrousel {
    display: none;
  }

  .title-section {
    display: none;
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
