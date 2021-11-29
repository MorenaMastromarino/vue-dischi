<template>
  <header class="d-flex align-items-center justify-content-between">

    <img src="../assets/img/spotify-logo.png" alt="spotify logo">

    <select class="form-select" v-model="genre" @change="$emit('changeSelectedGenre', genre)">
      <option selected>Selezionare un genere</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
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
      width: 20%;
    }
  }
</style>