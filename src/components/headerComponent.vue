<template>
  <header class="container-fluid p-2">
    <div class="row">
      <div class="col">
        <img class="img-fluid" src="@/assets/spotify-logo.png" alt="spotify-logo">
      </div>
      <div class="col">
        <div class="form-floating">
          <select @click="$emit('filteredAlbums', selected)" v-model="selected" class="form-select" id="floatingSelect" aria-label="Floating label select example">
            <option value="All">All</option>
            <option v-for="genre in genres" :key="genre" :value="genre">{{ genre }}</option>
          </select>
          <label for="floatingSelect">Select gender</label>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name:'headerComponent',
  data(){return{
    selected:'All'
  }},
  props:{
    genres: Array
  }
}
</script>

<style scoped lang="scss">
  @import '@/assets/variables.scss';

  header{
    background-color: $bg-header-card;
     img{
       width: 50px;
       height: auto;
     }
  }

</style>