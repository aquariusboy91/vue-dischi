
<template>
  <div class="container bg-main-color">
      <div class="row container-cards row-cols-5">
        <div v-for="(album, index) in cards" :key="index" class="col p-3">
          <img class="mb-2" :src="album.poster" :alt="album.title">
          <h2 class="text-light mb-3 text-uppercase fs-4">{{ album.title }}</h2>
          
        </div>

      </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Main',
  
  data() {
      return {
          cards: null
      }
    },
    created () {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(response => {
              this.cards = response.data.response;
              console.log(this.cards)
            })
            
    }
    
}
</script>


<style lang="scss" scoped>
    .bg-main-color {
        background-color: #1E2D3B;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .container-cards {
      width: 70%;
      margin: 0 auto;
    }
    img {
      width: 100%;
    }

</style>