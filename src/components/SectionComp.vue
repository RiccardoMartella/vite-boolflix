<script>
  import { store } from '../store'
  import CardsComp from './CardsComp.vue';

  export default{
    name: "SectionComp",
    data() {
      return {
        store: store,
      }
    },
    components:{
      CardsComp
    }
  }
</script>

<template>
  <div class=" p-4">
    <h3 class="ps-3">FILM</h3>
    <CardsComp />
  </div>
</template>

<style scoped lang="scss">
 div{
    background-color: rgb(9, 9, 9);
    height: 90vh;
    h3{
      color: rgb(100, 100, 100);
    }
 }
</style>
