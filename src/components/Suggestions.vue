<template>
    <div class="suggestions">
        <div>
            <p class="title_suggestion"><strong>Suggerimenti per te</strong></p>
            <p class="link">Mostra tutti</p>
        </div>


        <ul>
            <li v-for="(profile,index) in suggestions" :key="index">
                <div class="image_and_name">
                    <img :src="profile.profile_picture" alt="img-{profile}">
                     <p class="profile_name">{{profile.profile_name}}</p>
                </div>
                <div class="follow">
                    <p class="link">Segui</p>
                </div>
            </li>
        </ul>

        <footer>
            	&copy; 2020 INSTAGRAM FROM FACEBOOK
        </footer>
    </div>
</template>

<script>
export default {
  name: "Suggestions",
  props:{
      suggestions: Array
  },
    mounted(){
    }
};
</script>

<style lang="scss">
   .suggestions{
       width: 100%;
       padding: 0 0 0 50px;
       margin-top: 100px;


        div{
            display: flex;
            justify-content: space-between;
            
        }
        .link{
            font-weight: bold;
        }
        .link:hover{
            cursor: pointer;
        }
        .title_suggestion{
            color: #8F8F8F;
        }

        ul{
            list-style: none;
            
            li{
                display: flex;
                align-items: center;
                justify-content: space-between;
                margin-top: 20px;
                font-size: 14px;

                
                .profile_name{
                    margin-left: 20px;
                    font-weight: bold;
                }
                .image_and_name{
                    display: flex;
                    align-items: center;
                    justify-content: left;

                    img{
                        object-fit: cover;
                        width: 40px;
                        height: 40px;
                        border-radius: 50%;
                        }
                    }

                .follow{
                   color: deepskyblue; 
                    }    
            }
        }

        footer{
            margin-top: 50px;
            text-transform: uppercase;
            color: lightgrey;
            font-size: 14px;
            
        }
   }
</style>
