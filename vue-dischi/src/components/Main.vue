
<template>
  <div class="container bg-main-color">
      ciao
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Main',
  
  data() {
      return {
          cards: []
      }
    },
    creaded () {
        axios.get('https://flynn.boolean.careers/exercises/api/array')
            .then(response => {
              this.cards.push({ text : response.data.response});
              console.log("ciao")
              .catch(function (error) {
                console.log(error);
              });

            })
    }
}
</script>


<style lang="scss" scoped>
    .bg-main-color {
        background-color: #1E2D3B;
        height: 500px;
    }

</style>