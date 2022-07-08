<template>
  <div>
      <form @submit="submitData" method="post">
          <!-- <lable>Name: </lable> -->
          <input type="text" name="title" v-model="post.title"/> <br> <br>
          <input type="text" name="author" v-model="post.author" /> <br> <br>
            <button type="submit">Post</button>
      </form>
  </div>
</template>

<script>
// import * as Vue from 'vue' // in Vue 3
import Vue from 'vue'   // in Vue 2
import axios from 'axios'
import VueAxios from 'vue-axios'

Vue.use(VueAxios, axios) //Bind axios 3 files
export default {
    name: "Post-component",
    data()
    {
        return{
            post:{
                title:null,
                author:null
            }
          
        }
    },
    methods:{
        submitData(e){
            this.axios.post('http://localhost:3000/posts',this.post).then((result)=>{
                console.log("result",result)
            })
            console.log(this.post)
            e.preventDefault();
        }
    }
}
</script>

<style>

</style>