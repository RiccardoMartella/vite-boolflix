<script>
import { store } from '../store'
import CardComp from './CardComp.vue';
import axios from 'axios';

export default {
    name: "FilmListComp",
    data() {
        return {
            store: store,
        };
    },
    props: {
        url: String,
        storeKey: String,
        filmNameKey: String,
        filmOriginalNameKey: String,
        voteKey: String,
        languageKey: String,
    },
    mounted: function () {
        axios.get(`${this.url}?api_key=${import.meta.env.VITE_APP_TMDB_API_KEY}`)
            .then((response) => {
                store[this.storeKey] = response.data.results;
                store[`${this.storeKey}Filtered`] = response.data.results;
            });
    },
    methods: {},
    components: {
        CardComp
    }
}
</script>

<template>
    <div class="d-flex flex-wrap p-4">
        <CardComp :singleFilm="film" v-for="film in store[`${this.storeKey}Filtered`]" :filmNameKey="this.filmNameKey"
            :filmOriginalNameKey="this.filmOriginalNameKey" :voteKey="this.voteKey" :languageKey="this.languageKey"
            :key="film.id" />
    </div>
</template>

<style scoped lang="scss"></style>