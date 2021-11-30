<template>
  <div>
    <Header @changeSelectedGenre="sendSelectedGenre" :genresList="genres" />
    <Main :genre="selectedGenre" @getGenresList="sendGenresList" />
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
      selectedGenre: '',
      genres: [],
    }
  },
  methods:{
    sendSelectedGenre(genre){
      this.selectedGenre = genre;      
    },

    sendGenresList(genresList){
      this.genres = genresList;
    }
    
  }
}
</script>

<style lang="scss">
  @import './assets/style/vars.scss';
  @import './assets/style/generals.scss';

  
  

</style>
