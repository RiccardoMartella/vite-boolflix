<script >
  import axios from 'axios';
  import NavBarComp from './components/NavBarComp.vue';
  import { store } from './store'
  import SectionComp from './components/SectionComp.vue';

  export default{
    name: "AppVue",
    data() {
        return {
          store: store,
        };
    },
    components: { 
      NavBarComp,
      SectionComp,
    }
}
  
</script>

<template>
  <div class="contenitore-sfondo">
    <NavBarComp />
    <SectionComp />
  </div>
</template>

<style  lang="scss">
  @use './style/main.scss';
  .contenitore-sfondo{
    min-height: 100vh;
  }
</style>
