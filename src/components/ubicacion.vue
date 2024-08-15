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
      <iframe src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d3393.9178685806132!2d-106.4320536111425!3d31.71813846173373!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zMzHCsDQzJzA1LjMiTiAxMDbCsDI1JzU1LjUiVw!5e0!3m2!1ses-419!2smx!4v1723755532745!5m2!1ses-419!2smx" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
  </div>
</template>

<style>
.title-section-ubicacion {
  text-align: center;
  font-size: 1.8rem;
  font-family: 'quicksand', sans-serif;
  color: #2C2C30;
}

iframe {
  border-radius: 10px;
  margin: 1rem;
  max-width: 700px;
  border: 1px solid black;
}

@media (max-width: 900px) {
  .map-section {
    width: 100%;
    height: 500px;
    border: 1px solid red;
  }

  iframe {
    width: 100%;
    margin: 0;
    height: 100%;
  }
}
</style>