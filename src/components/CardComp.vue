<script>
import {
  store
} from '../store'

export default {
  name: "CardComp",
  data() {
    return {
      store: store,
      i: "FR",
    }
  },
  props: {
    singleFilm: Object,
    filmNameKey: String,
    filmOriginalNameKey: String,
    voteKey: String,
    languageKey: String,
  },
  methods: {
    getVote() {
      return Math.ceil(this.singleFilm[this.voteKey] / 2)
    },
    uppercaseText() {
      switch (this.singleFilm[this.languageKey]) {
        case 'en':
          return 'GB';
        case 'ja':
          return 'JP';
        case 'ko':
          return 'KP';
        default:
          return this.singleFilm[this.languageKey].toUpperCase()
      }
    }
  },
}
</script>

<template>
  <div class="contenitore-film">
    <img v-bind:src="'https://image.tmdb.org/t/p/w300' + singleFilm.poster_path" alt="">
    <h5>{{ singleFilm[filmNameKey] }}</h5>
    <div class="info">
      <h4>Titolo: {{ singleFilm[filmNameKey] }}</h4>
      <h4>Titolo Originale: {{ singleFilm[filmOriginalNameKey] }}</h4>
      <div class="d-flex align-items-center">
        <h4>Voto: {{ getVote() }}</h4>
        <i v-for="e in  5 " class="fa-star" :class="(e <= getVote()) ? 'fa-solid ' : 'fa-regular'"
          style=" color: #ffffff;"></i>
      </div>
      <h4>Lingua : {{ singleFilm[languageKey] }}</h4>
      <img v-bind:src="`https://flagsapi.com/${uppercaseText()}/flat/64.png`" alt="">
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

      i {
        padding-left: 8px;
        margin-bottom: 7px;
      }
    }
  }

}
</style>