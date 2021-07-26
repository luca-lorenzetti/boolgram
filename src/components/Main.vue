<template>
  <main>
    <div class="container">

      <div class="left">
        <Stories :dataStories="stories.slice(0,6)"/>
        <Posts :posts="posts"/>
      </div>
      <div class="right">
        <Profile :profile="profile"/>
        <Suggestions :suggestions="stories"/>
      </div>
    </div>
  </main>
</template>

<script>
import Stories from "@/components/Stories.vue";
import Profile from "@/components/Profile.vue";
import Posts from "@/components/Posts.vue";
import Suggestions from "@/components/Suggestions.vue";

import axios from 'axios';




export default {
  name: "Main",
    components: {
    Stories,
    Profile,
    Posts,
    Suggestions
  },
  data(){
    return{
      profile: {username: 'michelepapagni', first_name: 'Michele', last_name: 'Papagni', profile_image: 'profile.jpg'},
      stories: [],
      posts: []
    }
  },
  methods:{
    setStories(){
          axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
          .then( (response) => {
              // handle success
              this.stories = response.data;

              // console.log(response.data);
          })
          .catch(function (error) {
              // handle error
              console.log(error);
        });
    },

    setPosts(){
           axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts')
          .then( (response) => {
              // handle success
              this.posts = response.data;

              console.log(response.data);
          })
          .catch(function (error) {
              // handle error
              console.log(error);
        });
    } 
  },
  
  mounted() {
    this.setStories();
    this.setPosts();
  },


};
</script>

<style lang="scss">
.container{
  display: flex;
  width: 58%;
  margin: 0 auto;
  align-items: flex-start;

  & > div{
    margin-top: 100px;
  }

  .left{
    flex-basis: 60%;
  }

  .right{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    flex-basis: 40%;
    padding-left: 50px;
  }
}
</style>
