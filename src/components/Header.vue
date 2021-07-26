<template>

  <header class=" container-fluid">
    <nav>
      <img id="logo" alt="Vue logo" src="../assets/logo.png" />

      <input type="text" name="search" id="search" placeholder="Cerca">
      
      <div class="profile">
        <i class="material-icons">favorite_border</i>
        <i class="material-icons">home</i>
        <img src="../assets/profile.jpg" alt="icon-profile" class="profile_image">
      </div>
      

    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
  },
};
</script>

<style lang="scss">

  i:hover{
      cursor: pointer;
  }

  a{
    text-decoration: none;
    color: deepskyblue;
    font-weight: bold;
  }

  header{
    border-top: 1px solid #000;
    border-bottom: 1px solid #000;
    padding: 15px 0;

    nav{

      display: flex;
      justify-content: space-around;

      #search{
        border: 1px solid lavender;
        text-align: center;
      }


      #logo{
        width: 100px;
      }

      #logo:hover{
        cursor: pointer;
      }

      .profile{
        display: flex;
        align-items: center;
      }
      .profile{

        > * {
          margin: 0 10px;
        }

        > img:hover{
          cursor: pointer;
        }

      }

    }
  }
  .profile_image{
    width: 40px;
    border-radius: 50%;
  }
</style>
