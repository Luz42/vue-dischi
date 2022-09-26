<template>
  <div id="app" class="d-flex flex-column" style="height: 100vh;">
    <headerComponent/>
    <mainComponent :listAlbum="cards"/>
  </div>
</template>

<script>
import headerComponent from './components/headerComponent.vue';
import mainComponent from './components/mainComponent.vue';
import axios from 'axios';

export default {
  name: 'App',
  data(){return{
    cards:[]
  }},
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(({data, status})=>{
      if(status === 200){
        console.log(data.response)
        this.cards = data.response
        console.log(this.cards)
      }
      else{
        data.success = false
      }
    })

  },
  components: {
    headerComponent,
    mainComponent
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
