<script>
  import { store } from '../store'

  export default{
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
    <div>
      <img v-bind:src="'https://image.tmdb.org/t/p/w300' + singlefilm.poster_path" alt="">
      {{singlefilm.title }}
    </div>
</template>

<style scoped lang="scss">

</style>