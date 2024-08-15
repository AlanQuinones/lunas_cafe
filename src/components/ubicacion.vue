<script>
export default {
  name: 'Ubicacion',
  data() {
    return {
      model: 0,
      images: [
        // random places
        {
          src: 'https://img.rtve.es/imagenes/cafeterias-bonitas-espana-dia-internacional-cafe/1601401240006.jpg',
        },
        {
          src: 'https://mardomdecor.com/app/uploads/2023/03/CAFETERIA-2.jpeg',
        },
        {
          src: 'https://pisoocho.com.mx/wp-content/uploads/2020/06/Cafe-y-IPAD-horizontal-min-scaled.jpg',
        },
        {
          src: 'https://dynamic-media-cdn.tripadvisor.com/media/photo-o/11/8e/35/0e/tomate-cafe.jpg',
        },
      ]
    }
  }
}
</script>

<template>
  <h2 class="title-section-ubicacion" id="ubicacion">
    Ubicacion
  </h2>
  <div class="ubicacion">
    <div class="map-section">
      <iframe src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d3393.9178685806132!2d-106.4320536111425!3d31.71813846173373!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zMzHCsDQzJzA1LjMiTiAxMDbCsDI1JzU1LjUiVw!5e0!3m2!1ses-419!2smx!4v1723755532745!5m2!1ses-419!2smx" class="map" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
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