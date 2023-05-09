<script >
    import NavBarComp from './components/NavBarComp.vue';
    
  export default{
    name: "AppVue",
    data() {
        return {};
    },
    components: { 
      NavBarComp,
     
     }
}
  
</script>

<template>
  <NavBarComp />
</template>

<style lang="scss">
  @use './style/main.scss';
</style>
