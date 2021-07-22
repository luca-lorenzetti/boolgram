<template>
  <main>
    <div class="container">

      <div class="left">
        <Stories/>
      </div>
      <div class="right">
        
      </div>
    </div>
  </main>
</template>

<script>
import Stories from "@/components/Stories.vue";


export default {
  name: "Main",
    components: {
    Stories,
  },
  props: {
  },
};
</script>

<style lang="scss">
.container{
  display: flex;
  width: 80%;
  margin: 0 auto;

  &>div{
    margin-top: 150px;
  }
  .left{
    flex-basis: 50%;
    flex: 1;
  }
}
</style>
