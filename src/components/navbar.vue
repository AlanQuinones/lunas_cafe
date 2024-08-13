<script>
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiCoffee, mdiMapMarker } from '@mdi/js';

export default {
  name: 'Navbar',
  props: {
    title: {
      type: String,
      required: true
    }
  },

  //Importing the SvgIcon component
  name: "my-cool-component",

	components: {
		SvgIcon
	},

	data() {
		return {
	  		coffee: mdiCoffee,
        location: mdiMapMarker
		}
	}
}
</script>

<template>
  <nav class="navbar">
    <div class="container">
      <div class="navbar-brand">
        <a href="/" class="navbar-item">
          <h1>{{ title }}</h1>
        </a>
      </div>
    </div>

    <div class="nav-options">
      <v-btn stacked>
          <svg-icon type="mdi" :path="coffee"></svg-icon>
        Menu
      </v-btn>

      <v-btn stacked>
          <svg-icon type="mdi" :path="location"></svg-icon>
        Ubicacion
      </v-btn>
    </div>


  </nav>
</template>
<style>
.navbar {
  background-color: #B08969;
  padding: 1rem 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.navbar-item {
  text-decoration: none;
  color: #EDE0D4;
  border: 1px solid #EDE0D4;
  justify-content: center;
  align-items: center;
  display: flex;
  padding: 0.5rem;
  border-radius: 0.5rem;
  margin-left: 1rem;
}

.nav-options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  margin: 0 1rem;
}
</style>
