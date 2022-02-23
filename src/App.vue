<template>
  <div id="app">
    <MyHeader :messaggio="titoloApp"/>
    <ListaPersonaggi />
  </div>
</template>

<script>
  import ListaPersonaggi from './components/ListaPersonaggi.vue';
  import MyHeader from './components/MyHeader.vue';
  
  export default {
    name: 'App',
    components: {
      MyHeader,
      ListaPersonaggi
    },
    data() {
      return {
        titoloApp: 'Rick and Morty App',
      }
    }
  }
</script>

<style lang="scss">
    @import './style/general.scss';
</style>
