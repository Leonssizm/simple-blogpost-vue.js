<template>
    <h1 class="p-5 d-flex justify-content-center"> Add Post </h1>
    <div class="d-flex flex-column align-items-center ">
        <div class="form-group w-25 ">
            <input type="text" id="title" class="form-control mb-3" placeholder='Title' v-model="titleInputValue">
            <textarea id="body" class="form-control mt-3" placeholder="Body" v-model="bodyInputValue"></textarea>
        </div>
    </div>

    <div class="d-flex justify-content-center p-5 ">
        <button class="btn btn-primary mr-5"> Create </button>
        <router-link to="/posts" class="btn btn-danger "> Cancel </router-link>
    </div>
</template>

<!-- Under construction -->
<script>
export default {
    data() {
        return {
            titleInputValue: '',
            bodyInputValue: '',
        }
    },
  
}
</script>