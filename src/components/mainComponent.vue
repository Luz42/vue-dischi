<template>
  <main class="p-5 flex-grow-1">
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