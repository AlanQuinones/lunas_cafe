<script>
import jugos from '@/assets/jugos.jpeg'
import barra from '@/assets/barraMich.jpeg'
import entradaDesdeCalle from '@/assets/entradaDesdeCalle.jpeg'
import NumOficial from '@/assets/NumOficial.jpeg'
import PanMMOlla from '@/assets/PanMMOlla.jpeg'
import EspressoShot from '@/assets/EspressoShot.jpeg'
import panini from '@/assets/panini.jpeg'
import abierto from '@/assets/abierto.jpeg'
import panMuerto from '@/assets/panMuerto.jpeg'

export default {
  name: 'Ubicacion',
  data() {
    return {
      model: 0,
      images: [
        { src: barra, id: 1, title: 'Barra', description: 'Barra' },
        { src: entradaDesdeCalle, id: 2, title: 'entrada', description: 'entrada por calle' },
        { src: NumOficial, id: 3, title: 'num', description: 'num' },
        { src: PanMMOlla, id: 4, title: 'panMM', description: 'panMM' },
        { src: EspressoShot, id: 5, title: 'es', description: 'es' },
        { src: panini, id: 6, title: 'panini', description: 'panini' },
        { src: abierto, id: 7, title: 'abierto', description: 'abierto' },
        { src: panMuerto, id: 8, title: 'panMuerto', description: 'pan de muerto prro' },
        
      ]
    }
  }
}
</script>

<template>
  <h2 class="title-section-ubicacion">
    Ubicacion
  </h2>
  <div class="ubicacion">
    <div class="map-section">
      <!-- <iframe src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d3393.9178685806132!2d-106.4320536111425!3d31.71813846173373!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zMzHCsDQzJzA1LjMiTiAxMDbCsDI1JzU1LjUiVw!5e0!3m2!1ses-419!2smx!4v1723755532745!5m2!1ses-419!2smx" class="map" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      https://maps.app.goo.gl/nv8VnbXTG5U2pobS8 -->
      <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d17058.245357820906!2d-106.4440839!3d31.7166562!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x86e75d29bcba3a3b%3A0x80f928ea7be621bf!2sLuna&#39;s%20Caf%C3%A9!5e1!3m2!1sen!2smx!4v1726947249870!5m2!1sen!2smx" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
    <v-carousel class="carrousel">
      <v-carousel-item v-for="image in images" :src="image.src" cover class="carrousel-image">
      </v-carousel-item>
    </v-carousel>
    <v-carousel class="carrousel-phone" hide-delimiters>
      <v-carousel-item v-for="image in images" :src="image.src" cover class="carrousel-image">
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<style>
.map-section {
  width: 100%;
  height: 500px;
  margin-right: 2rem;
}

.title-section-ubicacion {
  text-align: center;
  font-size: 1.8rem;
  font-family: 'quicksand', sans-serif;
  color: #2C2C30;
}

iframe {
  border-radius: 10px;
  width: 100%;
  margin: 2rem;
  border: 0px solid black;
}

.carrousel {
  max-width: 700px;
  border-radius: 10px;
  margin: 2rem;
}

.carrousel-phone {
  display: none;
}

.ubicacion {
  display: flex;
}

.map {
  width: 100%;
  height: 500px;
}

@media (max-width: 900px) {
  .map-section {
    width: 90%;
    height: 500px;
    margin: 0;
  }
  
  iframe {
    margin: 0;
    height: 100%;
    max-width: none;
  }

  .ubicacion {
    flex-direction: column;
    align-items: center;
  }
  
  .carrousel-phone {
    max-width: 100%;
    margin: 1rem;
    display: block;
  }

  .carrousel {
    display: none;
  }
}
</style>