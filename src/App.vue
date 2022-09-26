<template>
  <div id="app">
    <headerComponent/>
    <mainComponent/>
  </div>
</template>

<script>
import headerComponent from './components/headerComponent.vue';
import mainComponent from './components/mainComponent.vue';

export default {
  name: 'App',
  components: {
    headerComponent,
    mainComponent
  }
}
</script>

<style lang="scss">
  @import './assets/main.scss';
    
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
