<template>
  <div class="container">
      <div v-for="(post, i) in posts" :key="i">
          <p>{{post.title}}</p>
          <p>{{post.image.url}}</p>
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

</style>
