<template>
    <div class="posts">
        <Single_post v-for="(post,index) in posts" :key="index" :single_post="post"/>
    </div>
</template>

<script>
import Single_post from "@/components/Single_post.vue";


export default {

  name: "Posts",
  components:{
    Single_post  
  },
  props:{
      posts: Array
  },
 
};
</script>

<style lang="scss">


    
</style>
