<template>
    <div class="stories">
        <div class="storie" v-for="storie in stories" :key="storie">
           <img :src="storie.profile_picture" alt="img-{storie}">
           <p class="profile_name">{{storie.profile_name}}</p>
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
  
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
    .then( (response) => {
        // handle success
        this.stories = response.data;

        // console.log(response.data);
        console.log(this.stories);

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
        border: solid lightgray 1px;
        display: flex;
        justify-content: center;
        align-items: center;

        .storie{
            display: flex;
            flex-direction: column;
            margin: 0 10px;
            text-align: center;

            img{
                width: 50px;
                padding: 1px;
                height: 50px;
                border-radius: 50%;
                border: 2px solid red;
            } 

            .profile_name{
                text-overflow: ellipsis;
                overflow: hidden; 
                width: 60px; 
                height: 1.2em; 
                white-space: nowrap;
                margin: 10px 0;
                font-size: 14px;
                font-weight: bold;
            }
        }  
    }
</style>
