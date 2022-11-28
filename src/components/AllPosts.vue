<template>
 <div>
    <h1 class="p-5 d-flex justify-content-center">Posts</h1>
    <div class='p-5 text-center'>
        <a href='create.html' class="btn btn-success">Add Post</a>
        <hr>
    </div>
 </div>
 <div>
    <span>{{posts.id}}</span>
    <h3>{{posts.title}}</h3>
    <p>{{posts.body}}</p>
        <div class="btn-wrapper d-flex justify-content-between mt-5 ">
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
    methods: {
        fetchAllPosts(){
            fetch('https://jsonplaceholder.typicode.com/posts')
            .then(response => response.json()).then((posts) =>{
                posts.forEach((post) => {
                   this.posts.push(post.id);
                   this.posts.push(post.title);
                   this.posts.push(post.body)
                })
            })
        },
    },
}
</script>



