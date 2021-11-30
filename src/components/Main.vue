<template>
  <main>
   
    <div class="container py-5">

      <div v-if="!isLoading" class="row row-cols-5 gx-4 gy-3" >
        <SongCard 
          v-for="(song, index) in selectedGenre"
          :key="index"
          :song = song
        />   
      </div>

      <Loader v-else />
      
    </div>

  </main>
</template>

<script>
import axios from 'axios';
import SongCard from './SongCard.vue';
import Loader from './Loader.vue';

export default {
  name: 'Main',

  props:{
    genre: String,
  },  

  components: {
    SongCard,
    Loader,
  },

  data(){
    return{
      songs: [],
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      isLoading: true,
      genres: [],
    }
  },

  methods: {
    getApi(){
      axios.get(this.apiUrl) 
      .then(r => {        
        this.songs = r.data.response;
        this.isLoading = false;

        this.songs.forEach(song => {
          if(!this.genres.includes(song.genre)){
            this.genres.push(song.genre);
          }
          
        });

        this.$emit('getGenresList', this.genres);
        
      })
      .catch(e => {
        console.log(e);
      })
    }
  },

  computed:{
    selectedGenre(){
      if(this.genre === ''){
        return this.songs;
      }
      return this.songs.filter(song => song.genre === this.genre);
    }
  },

  mounted(){
    this.getApi();
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