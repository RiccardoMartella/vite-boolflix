<script>
    import { store } from '../store'
    import Cardcomp from './Cardcomp.vue';
    import axios from 'axios';

    export default{
        name: "CardsComp",
        data() {
            return {
                store: store,
            };
        },
        mounted: function () {
            axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=${import.meta.env.VITE_APP_TMDB_API_KEY}`)
                .then((response) => {
                store.films = response.data.results;
            });
        },
        methods: {},
        components: { Cardcomp }
    }
</script>

<template>
 <div>
    <Cardcomp :singoloFilm="film" v-for="film in store.films" :key="film.id" />
 </div>
</template>

<style scoped lang="scss">

</style>