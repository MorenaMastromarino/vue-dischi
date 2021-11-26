<template>
  <div class="row row-cols-5 gx-4 gy-3" >

    <div class="col">
      <div class="card p-3 text-center">
        <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
        <h3 class="py-3">New jersey</h3>
        <p class="mb-0">Bon Jovi</p>
        <p class="">1988</p>
      </div>
    </div>     

  </div>
</template>

<script>
export default {
  name: 'SongsList',

}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars.scss';

  .card {
    background-color: $primary-color;
    
    
    h3 {
      text-transform: uppercase;
      font-size: 20px;      
    }
    p {
      font-size: 14px;
      color: #6B8080;
    }
  }
</style>