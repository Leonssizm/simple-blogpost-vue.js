<template>

<h1 class="p-5 d-flex justify-content-center">BlogPost</h1>
    <div class="card card-body p-5 d-flex justify-content-center ">
        <h2>{{currentPost.title}}</h2>
        <hr>
        <p>{{currentPost.body}}</p>
    </div>
    <router-link to="/posts" class="btn btn-primary m-5 float-right"> Go Back </router-link>

</template>

<script>
import { toRaw } from 'vue';

export default {


data(){
    return{
        posts:[],
        currentPost:[],
    }
},
mounted() {

    const postId = this.$route.params.id;

    fetch('https://jsonplaceholder.typicode.com/posts')
            .then(response => response.json()).then((posts) =>{
                this.posts.push(posts);
                
            const allPosts = toRaw(this.posts)[0];
            const selectedPost = allPosts.find(post => post.id === parseInt(postId));
            this.currentPost = selectedPost;
            
    });

},


}
</script>
