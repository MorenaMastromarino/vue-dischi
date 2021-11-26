<template>
  <header class="d-flex align-items-center">
    <img src="../assets/img/spotify-logo.png" alt="">
  </header>
</template>

<script>
export default {
  name: 'Header',

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
  }
</style>