<script>
import ScheduleComponent from '@/components/schedule-component.vue';


export default {
  name: 'Horario',
  components: {
    ScheduleComponent,
  },
  data(){
    return {
      shedule: [
        {
          day: 'Lunes',
          time: 'cerrado',
        },
        {
          day: 'Martes',
          time: 'cerrado',
        },
        {
          day: 'Miercoles',
          time: '5:00pm - 9:00pm',
        },
        {
          day: 'Jueves',
          time: '5:00pm - 9:00pm',
        },
        {
          day: 'Viernes',
          time: '5:00pm - 9:00pm',
        },
        {
          day: 'Sabado',
          time: '9:00am - 3:00pm',
        },
        {
          day: 'Domingo',
          time: '9:00am - 3:00pm',
        }
      ],
    }
  }
}

</script>

<template>
  <h2 class="title-section-menu">
      Horario
  </h2>
  <div class="menu-section">
    <div class="menu-section--drinks">
      <div v-for="days in shedule" class="menu-drinks">
        <ScheduleComponent :day="days.day" :time="days.time" class="drink"/>
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
