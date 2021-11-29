<template>
  <div>
    <Header @changeSelectedGenre="sendSelectedGenre"/>
    <Main :genre="selectedGenre" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return {
      selectedGenre:'',
    }
  },
  methods:{
    sendSelectedGenre(genre){
      this.selectedGenre = genre;
      console.log('genre in App', this.selectedGenre);
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/vars.scss';
  @import './assets/style/generals.scss';

  
  

</style>
