<template>
  <div id="app" class="d-flex flex-column" style="height: 100vh;">
    <headerComponent @filteredAlbums="filterGenre" :genres="listGenre"/>
    <loadingComponent v-if="loading"/>
    <mainComponent v-else-if="cards.length !== 0" :listAlbum="cardsToDisplay"/>
    <errorComponent :message="errorMessage" v-else/>
  </div>
</template>

<script>
import headerComponent from './components/headerComponent.vue';
import mainComponent from './components/mainComponent.vue';
import loadingComponent from './loadingComponent.vue';
import errorComponent from './errorComponent.vue';
import axios from 'axios';

export default {
  name: 'App',
  data(){return{
    cards:[],
    cardsToDisplay:[],
    loading: true,
    errorMessage:'',
    listGenre:[]
  }},
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(({data, status})=>{

      if(status === 200){
        this.loading = false
        //console.log(data.response)
        this.cards = data.response
        this.cardsToDisplay = data.response
        console.log(this.cards)
        //creo un array con i generi degli album per andare a creare le opzioni
        //inizializzo l'array
        data.response.forEach(album => {
          //se l'elemento non è già all'interno dell'array lo pusho
          if(!this.listGenre.includes(album.genre)){
            this.listGenre.push(album.genre)
          }
        });
      }
      else{
        this.loading = false
      }
      console.log(this.listGenre)         

    }).catch(error=>{
      console.log(error)
      this.loading = false
      this.errorMessage = 'Errore: ' + error.message;
    })
  },
  methods:{
    filterGenre(typeGenre){
      console.log(typeGenre)
      this.cardsToDisplay = this.cards          

      if(typeGenre !== 'All'){
        this.cardsToDisplay = this.cardsToDisplay.filter(album=> album.genre == typeGenre)
      }

    }
  },
  components: {
    headerComponent,
    mainComponent,
    loadingComponent,
    errorComponent
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
