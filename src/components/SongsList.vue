<template>
  <div class="row row-cols-5 gx-4 gy-3" >

    <SongCard 
      v-for="(song, index) in songs"
      :key="index"
      :song = song
    />
    

  </div>
</template>

<script>
import axios from 'axios';
import SongCard from './SongCard.vue';

export default {
  name: 'SongsList',
  components: {
    SongCard,
  },
  data(){
    return{
      songs: [],
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
    }
  },
  methods: {
    getApi(){
      axios.get(this.apiUrl)
      .then(r => {
        
        this.songs = r.data.response;
    
      })
      .catch(e => {
        console.log(e);
      })
    }
  },
  mounted(){
    this.getApi();
  }
}
</script>

<style lang="scss" scoped>
 
</style>