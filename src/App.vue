<template>
  <div id="app" class="d-flex flex-column" style="height: 100vh;">
    <headerComponent/>
    <loadingComponent v-if="loading"/>
    <mainComponent v-else :listAlbum="cards"/>
  </div>
</template>

<script>
import headerComponent from './components/headerComponent.vue';
import mainComponent from './components/mainComponent.vue';
import loadingComponent from './loadingComponent.vue';
import axios from 'axios';

export default {
  name: 'App',
  data(){return{
    cards:[],
    loading: true
  }},
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(({data, status})=>{

      if(status === 200){
        this.loading = false
        console.log(data.response)
        this.cards = data.response
        console.log(this.cards)
      }
      else{
        this.loading = false
        data.success = false
      }
    })

  },
  components: {
    headerComponent,
    mainComponent,
    loadingComponent
  },
}
</script>

<style lang="scss">
  @import './assets/main.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
