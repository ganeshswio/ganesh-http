<template>
  <div class="hello">

    <label for="title">Blog title :</label>
    <input type="text" v-model="title"> <br> <br>
    <label for="content">Blog content :</label>
    <input type="text" v-model="content">
    <h1>Preview Blog</h1>
    <p>BlogTitl :{{title}}</p>
    <p>Blog Content: {{content}}</p>
    
    <p>Blog Categories :</p>
    <ul>
      
      <!-- <li v-for="category in blog.categories">{{categories}}</li> -->
    </ul>

    <button v-on:click.prevent="post">POST BLOG</button>
    
     
  </div>
</template>



<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
     
     
        title:"",
        content:"",
        categories:[],
        author:"",
   
    }
   
  },
  methods:{
    post(){
       this.$http.post("http://jsonplaceholder.typicode.com/posts",{
         title:this.title,
         body:this.content,
         userid:1
       }).then(function(data){
         
         console.log(data);
       });
    }
    
  }
}
</script>




<style scoped>

</style>
