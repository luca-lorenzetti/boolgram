<template>
    <div class="post">
        <div class="post_header">
            <div class="left_header_post">
                <img :src="single_post.profile_picture" alt="img_profile" class="profile_image">
                <span class="profile_name">{{single_post.profile_fullname}}</span>
            </div>
            <div class="right_header_post">
                <i class="material-icons">more_horiz</i>
            </div>
        </div>
            <img :src="single_post.post_image" alt="pictures_post" class="picture_post">
             <div class="content_post">
                <div class="like">
                    <div class="icons_likes">
                        <i class="material-icons">favorite_border</i>
                        <i class="material-icons">chat_bubble_outline</i>
                    </div>
           
                    <div class="likes_profiles">
                        <img class="profile_image_like" :src="single_post.likes[single_post.likes.length-1].profile_picture" alt="img_profile_like">
                        Piace a<strong>{{single_post.likes[single_post.likes.length-1].username}}</strong><span v-show="single_post.likes.length > 0">e<strong>{{single_post.likes.length}} altri </strong></span>
                    </div>

                </div>
                <div class="text_post">
                    <p><strong>{{single_post.profile_name}}</strong>{{single_post.post_text}}</p>
                </div>
                <div class="comments">
                    <p class="all_comments">Mostra tutti e {{single_post.comments.length}} commenti</p>
                    <ul>
                        <li v-for="i in 4" :key="i"> <strong>{{single_post.comments[i].username}}</strong>{{single_post.comments[i].text}}</li>
                    </ul>
                </div>
            </div>
         
    </div>
</template>

<script>

export default {
  name: "Posts",
  props:{
      single_post: Object
  },
    mounted(){
    }
};
</script>

<style lang="scss">

 
    strong::before, strong::after, p.all_comments::before{
        content: " ";
        white-space: pre;
    }
    .post{
        border: solid lightgray 1px;
        display: flex;
        flex-direction: column;
        margin-top: 50px;
        
        &>:not(img){
            padding: 15px 20px;
        }


        > img{
            object-fit: cover;
        }
        .post_header{
            display: flex;
            flex-basis: 100%;
            align-items: center;
            justify-content: space-between;

            .left_header_post{
                display: flex;
                align-items: center;
                

                .profile_name{
                    font-size: 16px;
                    font-weight: bold;
                    margin-left: 10px;
                }

                img{
                    width: 60px;
                    padding: 1px;
                    height: 60px;
                    border-radius: 50%;
                    object-fit: cover;
                    border: 2px solid red;
                }
            }
        }
        .content_post{
            display: flex;
            flex-direction: column;

            .like{
                display: flex;
                padding: 10px 0;
                flex-direction: column;
                font-size: 14px;

                .icons_likes{
                    display: flex;
                    justify-content: flex-start;
                    height: 40px;

                    > *{
                        margin-right: 10px; 
                        margin-bottom: 30px;
                    }
                }
                img.profile_image_like{
                    width: 30px;
                    height: 30px;
                    border-radius: 50%;
                    margin-right: 10px;
                    object-fit: cover;
                }
                .likes_profiles{
                    display: flex;
                    justify-content: flex-start;
                    align-items: center;
                }
            }
            .text_post{
                margin-top: 10px;
                font-size: 14px;
                text-align: left;
            }
        }
        .all_comments{
            color: lightgray;
            margin-top: 10px;
            text-align: left;

        }
       
        ul{
            font-size: 14px;
            list-style: none;
        }
        ul > li{
            text-align: left;
            margin: 5px 0;
        }
    }
</style>
