<script>
    import { store } from '../store'
    import CardComp from './CardComp.vue';
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
                console.log(store.films);
            });
        },
        methods: {},
        components: { CardComp }
    }
</script>

<template>
 <div>
    <CardComp :singlefilm="film" v-for="film in store.films" :key="film.id" />
 </div>
</template>

<style scoped lang="scss">

</style>