<template>
  <header class="p-2">
    <img class="img-fluid" src="@/assets/spotify-logo.png" alt="spotify-logo">
  </header>
</template>

<script>
export default {
  name:'headerComponent'
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