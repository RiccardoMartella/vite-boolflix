<script>
import { store } from '../store'

export default {
  name: "NavBar",
  data() {
    return {
      store: store,
      cerca: "",
    }
  },
  mounted: function () { },
  methods: {
    filtra() {
      store.filmsFiltered = store.films.filter((film) => {
        return film.title.toLowerCase().includes(this.cerca.toLowerCase())
      })

      store.seriesFiltered = store.series.filter((film) => {
        return film.original_name.toLowerCase().includes(this.cerca.toLowerCase())
      })
    }
  }
}
</script>

<template>
  <div class="d-flex justify-content-between p-4 contenitore-titolo">
    <div>
      <h1>NETFLIX</h1>
    </div>
    <div class="d-flex align-items-center">
      <input class="p-1" type="text" placeholder="cerca" v-model="cerca">
      <button @click="filtra()" class=" p-1 ps-2 ms-2">Inizia Ricerca</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.contenitore-titolo {
  background-color: rgb(18, 18, 18);
  border-bottom: 2px solid rgb(245, 41, 41);
  min-height: 10vh;

  h1 {
    color: red;
    text-shadow: 4px 4px 1px rgb(5, 5, 5);
  }
}

button:hover {
  color: red;
}
</style>