<template>
    <div class="stories">
        <div class="storie" v-for="storie in stories" :key="storie">
           <img :src="storie.profile_picture" alt="img-{storie}">
        </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Stories",
  data(){
      return{
          stories: []
      }
  },
  
  mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
    .then(function (response) {
        // handle success
        this.stories = response.data;

        console.log(response.data);
        console.log( this.stories);

    })
    .catch(function (error) {
        // handle error
        console.log(error);
  })
  }
};
</script>

<style lang="scss">
    .stories{
        height: 300px;
        border: solid red 1px;
        display: flex;
    }
</style>
