<template>
  <div class="col">
    <div class="card p-4 text-center">
      <img :src="song.poster" :alt="song.title">
      <h3 class="pt-4 pb-3">{{song.title}}</h3>
      <p class="mb-0">{{song.author}}</p>
      <p class="mb-0">{{song.year}}</p>
    </div>
  </div>     
</template>

<script>


export default {
  name: 'SongCard',
  props: {
    song: Object,
  }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

  .card {
    height: 100%;
    background-color: $primary-color;
    cursor: pointer;    
    
    h3 {
      text-transform: uppercase;
      font-size: 20px;      
    }

    p {
      font-size: 16px;
      color: #6B8080;
    }
  }
</style>