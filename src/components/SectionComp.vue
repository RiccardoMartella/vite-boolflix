<script>
import { store } from '../store'
import CardsCompFilm from './CardsCompFilm.vue';
import CardsCompSerie from './CardsCompSerie.vue';

export default {
  name: "SectionComp",
  data() {
    return {
      store: store,
    }
  },
  components: {
    CardsCompFilm,
    CardsCompSerie,
  }
}
</script>

<template>
  <div class=" p-4">
    <h3 class="ps-3">FILM</h3>
    <CardsCompFilm />
    <h3 class="ps-3 py-2">SERIE TV</h3>
    <CardsCompSerie />
  </div>
</template>

<style scoped lang="scss">
.p-4 {
  background-color: rgb(9, 9, 9);
  min-height: 90vh;

  h3 {
    color: rgb(100, 100, 100);
  }
}
</style>