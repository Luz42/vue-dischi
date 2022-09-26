<template>
  <main class="container-fluid flex-grow-1">
    <div class="row p-5 gap-4 d-flex justify-content-center">
        <cardComponent :card="album" v-for="album in listAlbum" :key="album.title" />
    </div>
  </main>
</template>

<script>
import cardComponent from './cardComponent.vue';

export default {
    name:'mainComponent',
    components:{
        cardComponent
    },
    props:{
        listAlbum: Array
    }
}
</script>

<style scoped lang="scss">
  @import '@/assets/variables.scss';


    main{
        background-color: $bg-main;
    }
</style>