<template>
  <header class="d-flex align-items-center justify-content-between">

    <img src="../assets/img/spotify-logo.png" alt="spotify logo">

    <select class="form-select" v-model="genre" @change="$emit('changeSelectedGenre', genre)">
      <option value="" selected>Selezionare un genere</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>

  </header>
</template>

<script>
export default {
  name: 'Header',

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