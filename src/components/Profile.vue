<template>
    <div class="profile_main">
        <img :src="require('@/assets/'+profile.profile_image)" class="profile_image" alt="img_profile">
        <div class="profile_names">
            <p id="username">{{profile.username}}</p>
            <p id="fullname">{{profile.first_name}} {{profile.last_name}}</p>
        </div>
        <a href="#">Passa a</a>
    </div>
</template>

<script>
export default {
  name: "Profile",
  props:{
      profile: Object
  },

};
</script>

<style lang="scss">
    .profile_main{
        margin-top: 30px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-basis: 100%;
        padding: 0 0 0 50px;

        img{
            width: 60px;
            object-fit: contain;
        }
        #username{
          font-weight: bold;  
        }

        #fullname{
            margin-top: 5px;
            color: #8F8F8F;
        }
    }
</style>
