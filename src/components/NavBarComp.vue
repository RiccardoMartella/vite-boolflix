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
  <div class="d-flex justify-content-between p-4">
    <div>
    <h1>NETFLIX</h1>
    </div>
    <div class="d-flex align-items-center">
      <input class="p-1" type="text" placeholder="cerca">
      <button class="ps-2 ms-2">INVIO</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
   .justify-content-between{
    background-color: rgb(28, 28, 28);
    box-shadow: 0px 3px 3px red;
      h1{
        color: red;
      }
   }
</style>
