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
    singlefilm: Object
  }
}
</script>

<template>
  <div class="contenitore-film">
    <img v-bind:src="'https://image.tmdb.org/t/p/w300' + singlefilm.poster_path" alt="">
    <h5>{{ singlefilm.title }}</h5>
  </div>
</template>

<style scoped lang="scss">
.contenitore-film {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  margin: 10px;
  width: calc((100% / 5) - 20px);
  border: 1px solid rgb(77, 77, 77);
  border-radius: 5px;

  h5 {
    color: rgb(226, 226, 226);
    padding: 10px;
  }
}
</style>