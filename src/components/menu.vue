<script>
import FoodComponent from '@/components/food-component.vue';
import { mdiFoodForkDrink } from '@mdi/js';

export default {
  name: 'Menu',
  components: {
    // SvgIcon,
    FoodComponent,
  },
  data(){
    return {
      drinks: [
        {
          name: 'Latte',
          price: 75,
        },
        {
          name: 'Capuccino',
          price: 85,
        },
        {
          name: 'Americano',
          price: 50,
        },
        {
          name: 'Mocha',
          price: 90,
        },
        {
          name: 'Orange Coffee',
          price: 65,
        },
        {
          name: 'Agua de limon',
          price: 45,
        }
      ],
      foods: [
        {
          name: 'Panini',
          price: 145,
          description: 'Sandwich de pan panninin, peperoni, jamon de pavo, queso manchego, tomate deshdiratado. *incluye papas/chips'
        },
        {
          name: 'Paninni Pizza',
          price: 160,
          description: 'Sandwich de pan pannini, peperoni, espinaca, salsa de tomate y queso mozarrella. *incluye papas/chips'
        },
        {
          name: 'Galleta Nutella',
          price: 45,
          description: 'Galleta de chispas de chocolate rellena de nutella. *Se recomienda pedir caliente'
        },
        {
          name: 'Galleta Chispas',
          price: 45,
          description: 'Galleta de chispas de chocolate. *Se recomeinda Pedir caliente'
        },
        {
          name: 'Pay de Queso',
          price: 75,
          description: 'rebanada de pay de queso con amaretto'
        },
      ],
      foodIcon: mdiFoodForkDrink
    }
  }
}

</script>

<template>
  <h2 class="title-section-menu">
      Menu
  </h2>
  <div class="menu-section">
    <div class="menu-section--drinks">
      <h2 class="menu-title">Bebidas</h2>
      <div v-for="drink in drinks" class="menu-drinks">
        <FoodComponent :name="drink.name" :price="drink.price" class="drink"/>
      </div>
    </div>
    <div class="menu-section--foods">
      <h2 class="menu-title">Comida</h2>
      <div v-for="food in foods" class="menu-foods">
        <FoodComponent :name="food.name" :price="food.price" :description="food.description" class="food"/>
      </div>
    </div>
  </div>
</template>

<style>
.menu-section{
  display: flex;
  justify-content: space-between;
}

.menu-title{
  font-size: 2rem;
  margin: 1rem;
}

.menu-section--drinks,
.menu-section--foods {
  margin: 1rem;
  min-width: 300px;
  border: 1px solid black;
  border-radius: 20px;
  width: 50%;
}

.menu-drinks,
.menu-foods {
  margin: 1rem;
}

.drink {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 1rem;
  font-size: .7rem;
}

.food {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-areas:  "name              price"
                        "description description";
  justify-content: space-between;
  align-items: center;
  padding: 0 1rem;
  font-size: .7rem;
}

.price {
  grid-area: price;
  text-align: right;
}

.description{
  grid-area: description;
  font-size: .9rem;
}

.title-section-menu {
  text-align: center;
  font-size: 1.8rem;
  font-family: 'quicksand', sans-serif;
  color: #2C2C30;
}

.food-icon {
  color: #2C2D30;
}

@media (max-width: 900px) {
  .menu-section {
    flex-direction: column;
    width: 100%;
    margin-top: 300px;
  }
  .menu-section--foods,
  .menu-section--drinks {
    width: 90%;
    align-self: center;
    margin: 0%;
    margin-top: 1rem;
  }

  .title-section-menu {
    border-radius: 20px;
    margin-top: 330px;
    margin-bottom: -300px;
  }
}
</style>
