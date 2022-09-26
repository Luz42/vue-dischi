<template>
  <div class="col-2 p-3 text-center">
    <img class="img-fluid" :src="card.poster" alt="">
    <h6 class="text-uppercase py-3">{{card.title}}</h6>
    <div style="color:#797d7e">
        <p class="m-0">{{card.author}}</p>
        <p>{{card.year}}</p>
    </div>
  </div>
</template>

<script>
export default {
    name: 'cardComponent',
    props:{
        card: Object
    }
}
</script>

<style  scoped lang="scss">
  @import '@/assets/variables.scss';

  div{
    background-color: $bg-header-card;
    h6{
        color: white;
        font-weight: bold;
    };
    p,
    h6{
        font-size: 0.8em;
    }

  }

</style>