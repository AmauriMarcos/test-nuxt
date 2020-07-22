<template>
  <div class="container">
      <div v-for="(post, i) in posts" :key="i">
          <p>{{post.title}}</p>
        
          <img :src="`${post.image.name}`" alt="">
      </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
   async asyncData(){
     const res = await axios.get("https://test-santos.herokuapp.com/posts")
     return{posts: res.data}
   }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

img{
  width: 250px;
  height: 300px;
}

</style>
