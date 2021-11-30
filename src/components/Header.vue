<template>
  <header class="d-flex align-items-center justify-content-between">

    <img src="../assets/img/spotify-logo.png" alt="spotify logo">

    <select class="form-select" v-model="genre" @change="$emit('changeSelectedGenre', genre)">
      <option value="" selected>Selezionare un genere</option>
      <option 
        v-for="(genre, index) in genresList" 
        :key="index" 
        :value="genre"        
      >{{genre}}</option>      
      
    </select>

  </header>
</template>

<script>
export default {
  name: 'Header',

  props: {
    genresList: Array,
  },

  data(){
    return {
      genre: '',
    }
  }
  
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';

  header {
    height: 70px;
    padding: 0 20px;
    background-color: $primary-color;
    img {
      width: 45px;
    }
    select {
      width: auto;
    }
  }
</style>