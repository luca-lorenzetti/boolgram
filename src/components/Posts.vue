<template>
    <div class="posts">
        <Single_post v-for="post in posts" :key="post" :single_post="post"/>
    </div>
</template>

<script>
import Single_post from "@/components/Single_post.vue";


export default {
  watch: {
  },
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
