<script>
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';
  
  export default {
    name: 'AppVue',
    components:{
        AppHeader,
        AppMain,
      }
  }
</script>

<template>
  <div>
    <AppHeader/>
    <AppMain/>
  </div>
</template>

<style lang="scss">
  @import "bootstrap/scss/bootstrap";
  @import './styles/general.scss';

</style>
