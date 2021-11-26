<template>
  <main>
   
    <div class="container py-5">

      <SongsList />      

    </div>

  </main>
</template>

<script>
import SongsList from './SongsList.vue';

export default {
  name: 'Main',

  components: {
    SongsList,

  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';

  main {
    min-height: calc(100vh - 70px);
    background-color: darken($primary-color, 6%);
    color: #fff;    
    
  }
</style>