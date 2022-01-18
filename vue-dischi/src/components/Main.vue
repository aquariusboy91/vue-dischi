
<template>
  <div class="container bg-main-color">
      <div class="row justify-content-center pt-3">
        <select name="cars" id="cars" class="w-25" @change="filteredAlbum($event)" v-model="key">
          <option value ="Tutti"> Tutti</option>
          <option value ="Rock"> Rock</option>
          <option value ="Pop"> Pop</option>
          <option value ="Metal"> Metal</option>
          <option value ="Jazz"> Jazz</option>
        </select>
      </div>
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
          cards: null,
          key: "" ,
          filteredcards: null,
          all:'',

      }
    },
    created () {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(response => {
              this.cards = response.data.response;
              this.all = response.data.response;
              this.filteredcards = response.data.response;
              console.log(this.cards)
            })
            
    },
    methods: {
        filteredAlbum(event) {
          if (event.target.value === 'Tutti') {
            this.cards = this.all;
           return this.cards;
      } else {
        return this.cards = this.filteredcards.filter((element) => element.genre.includes(event.target.value));
      }
          
           
    }
    }
    
    
}
</script>


<style lang="scss" scoped>
    .bg-main-color {
        background-color: #1E2D3B;
        height: 100vh;
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