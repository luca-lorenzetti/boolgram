<template>
    <div>
        <div class="stories">
                <div class="storie" v-for="(storie, index) in dataStories" :key="index">
                    <img :src="storie.profile_picture" alt="img-{storie}">
                    <p class="profile_name">{{storie.profile_name}}</p>
                </div>
        </div>
    </div>
   
</template>

<script>
export default {
  name: "Stories",
  props:{
      dataStories: Array
  },


};
</script>

<style lang="scss">
    .stories{
        height: 180px;
        border: solid lightgray 1px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        padding: 50px 50px 20px 50px;

        .storie{
            display: flex;
            flex-direction: column;
            text-align: center;

            img{
                object-fit: cover;
                width: 60px;
                padding: 1px;
                height: 60px;
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
                font-size: 12px;
                font-weight: bold;
            }
        }  
    }
</style>
