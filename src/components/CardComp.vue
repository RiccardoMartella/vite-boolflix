<script>
import {
  store
} from '../store'

export default {
  name: "CardComp",
  data() {
    return {
      store: store,
    }
  },
  props: {
    singlefilm: Object,
    filmNameKey: String,
    filmOriginalNameKey: String,
    votekey: Number,
    languageKey: String,
  }
}
</script>

<template>
  <div class="contenitore-film">
    <img v-bind:src="'https://image.tmdb.org/t/p/w300' + singlefilm.poster_path" alt="">
    <h5>{{ singlefilm[filmNameKey] }}</h5>
    <div class="info">
      <h4>Titolo: {{ singlefilm[filmNameKey] }}</h4>
      <h4>Titolo Originale: {{ singlefilm[filmOriginalNameKey] }}</h4>
      <h4>Voto :{{ singlefilm[votekey] }}</h4>
      <h4>Lingua : {{ singlefilm[languageKey] }}</h4>
    </div>
  </div>
</template>

<style scoped lang="scss">
.contenitore-film {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  margin: 10px;
  position: relative;
  width: calc((100% / 5) - 20px);
  border: 1px solid rgb(77, 77, 77);
  border-radius: 5px;

  h5 {
    color: rgb(226, 226, 226);
    padding: 10px;
  }

  .info {
    display: none;
  }

  &:hover {
    .info {
      display: block;
      position: absolute;
      top: 0;
      right: 0;
      left: 0;
      bottom: 0;
      background-color: rgb(26, 26, 26);
      border-radius: 5px;
      padding: 20px;

      h4 {
        color: white;
        margin: 10px 0 20px 0;
      }
    }
  }

}
</style>