<script>
import FilmListComp from './FilmListComp.vue';

export default {
  name: "CardsCompFilm",
  methods: {},
  components: {
    FilmListComp
  }
}
</script>

<template>
  <FilmListComp :url="'https://api.themoviedb.org/3/movie/popular'" :storeKey="'films'" />
</template>

<style scoped lang="scss"></style>
