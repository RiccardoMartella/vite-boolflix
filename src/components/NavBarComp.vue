<script>
  import { store } from '../store'

  export default{
    name: "NavBar",
    data() {
      return {
        store: store,
      }
    },
    mounted: function() {
    },
    methods: {
  
    }
  }
</script>

<template>
  <div class="d-flex justify-content-between p-4 contenitore-titolo">
    <div>
    <h1>NETFLIX</h1>
    </div>
    <div class="d-flex align-items-center">
      <input class="p-1" type="text" placeholder="cerca">
      <button class=" p-1 ps-2 ms-2">INVIO</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
   .contenitore-titolo{
    background-color: rgb(18, 18, 18);
    box-shadow: 0px 3px 3px red;
    height: 10vh;
      h1{
        color: red;
        text-shadow: 4px 4px 1px rgb(5, 5, 5) ;
      }
   }
</style>
