<script>
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiCoffee, mdiMapMarker, mdiMenu } from '@mdi/js';

export default {
  name: 'Navbar',
  props: {
    titlePage: {
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
        location: mdiMapMarker,
        menu: mdiMenu,
        sections: [
          { title: 'Inicio', path: '#inicio' },
          { title: 'Menu', path: '#menu' },
          { title: 'Ubicacion', path: '#ubicacion' },
          { title: 'Contacto', path: '#contacto' }
        ]
		}
	}
}
</script>

<template>
  <nav class="navbar">
    <div class="container">
      <div class="navbar-brand">
        <a href="/" class="navbar-item">
          <h1>{{ titlePage }}</h1>
        </a>
      </div>
    </div>

    <div class="nav-options">
      <button stacked v-for="section in sections" :key="section.title">
        <a :href="section.path" class="links">
          {{ section.title }}
        </a>
      </button>
    </div>

    <v-menu>
      <template v-slot:activator="{ props }">
        <button
          color="primary"
          v-bind="props"
          class="nav-options--phone"
           >
          <svg-icon type="mdi" :path="menu"></svg-icon>
        </button>
      </template>
      <v-list>
        <v-list-item
          v-for="(section, index) in sections"
          :key="index"
          :value="index"
        >
          <v-list-item-title>
            <a :href="section.path" class="links">
              {{ section.title }}
            </a>
          </v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>

  </nav>
</template>
<style>
.navbar {
  background-color: #7F5539;
  padding: 1rem 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  z-index: 1000;
  width: 100%;
}

.links {
  text-decoration: none;
  color: #EDE0D4;
  font-size: 1.2rem;
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
  text-decoration: none;
  color: #EDE0D4;
}

.nav-options--phone {
  display: none;
}

@media (max-width: 900px) {
  .nav-options {
    display: none;
  }
  .nav-options--phone {
    display: flex;
    background-color: #EDE0D4;
    color: #7F5539;
    border: 1px solid #7F5539;
    width: 100px;
    height: 50px;
    font-size: 15px;
    border-radius: 0.5rem;
    margin-right: 1rem;
    align-items: center;
    justify-content: center;
  }
}
</style>
