<script >
  import axios from 'axios';
  import NavBarComp from './components/NavBarComp.vue';
  import { store } from './store'

  export default{
    name: "AppVue",
    data() {
        return {
          store: store,
        };
    },
    mounted: function() {
      axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=${import.meta.env.VITE_APP_TMDB_API_KEY}`)
      .then((response) => {
        store.films = response.data.results;
        console.log(store.films)
      })
    },
    components: { 
      NavBarComp,
    }
}
  
</script>

<template>
  <NavBarComp />
 
</template>

<style lang="scss">
  @use './style/main.scss';
</style>
