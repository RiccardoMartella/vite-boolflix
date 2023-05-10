<script>
import { store } from '../store'
import CardComp from './Cardcomp.vue';
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
        storeKey: String
    },
    mounted: function () {
        axios.get(`${this.url}?api_key=${import.meta.env.VITE_APP_TMDB_API_KEY}`)
            .then((response) => {
                store[this.storeKey] = response.data.results;
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
        <CardComp :singlefilm="film" v-for="film in store[storeKey]" :key="film.id" />
    </div>
</template>

<style scoped lang="scss"></style>