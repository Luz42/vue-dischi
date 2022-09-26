<template>
  <main class="flex-grow-1">
    MAIN
    <cardComponent/>
  </main>
</template>

<script>
import cardComponent from './cardComponent.vue';

export default {
    name:'mainComponent',
    components:{
        cardComponent
    }
}
</script>

<style scoped lang="scss">
  @import '@/assets/variables.scss';


    main{
        background-color: $bg-main;
    }
</style>