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
            e.preventDefault()
        }
    }
}
</script>

<style>

</style>