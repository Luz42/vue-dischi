<template>
  <div class="flex-grow-1 flex-column d-flex justify-content-center align-items-center">

    <h3>{{ message }}</h3>
    <h5 class="text-uppercase my-3">sorry for the inconvenience, we are working for you</h5>

  </div>
</template>

<script>
export default {
    name:'errorComponent',
    props:{
        message: String
    }
}
</script>

<style scoped lang="scss">
    @import '@/assets/variables.scss';
    div{
        background-color: $bg-main;
        color: white;
    }
</style>