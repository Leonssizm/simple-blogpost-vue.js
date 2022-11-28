<template>
 <div>
    <h1 class="p-5 d-flex justify-content-center">Posts</h1>
    <div class='p-5 text-center'>
        <a href='create.html' class="btn btn-success">Add Post</a>
    </div>
 </div>
 <div v-for="post in posts" :key="post.id" class="container border border-3 rounded mt-3">
    <p class="mt-2">Post N{{post.id}}</p>
    <h3 class="d-flex justify-content-center mt-3">{{post.title}}</h3>
    <p class="mt-4">{{post.body}}</p>
        <div class="btn-wrapper d-flex justify-content-around mb-3 mt-3">
            <a class="btn btn-primary">View</a>
            <button class="btn btn-danger">Delete</button>
        </div>
</div>
 
</template>

<script>

export default {
    data() {
        return {
          posts:[],
        }
    },
    mounted() {
            fetch('https://jsonplaceholder.typicode.com/posts')
            .then(response => response.json()).then((posts) =>{
                this.posts = posts
        });
            
    },
}
</script>



