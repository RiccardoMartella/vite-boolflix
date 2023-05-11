<script>
import FilmListComp from './FilmListComp.vue';

export default {
  name: "CardsCompSerie",
  methods: {},
  components: {
    FilmListComp
  }
}
</script>

<template>
  <FilmListComp :url="'https://api.themoviedb.org/3/tv/top_rated'" :storeKey="'series'" :filmNameKey="'name'"
    :filmOriginalNameKey="'original_name'" :votekey="'vote_average'" :languageKey="'original_language'" />
</template>

<style  scoped lang =" scss">
    </style>
