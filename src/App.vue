<template>
 <router-view></router-view>
</template>

<script>

import Home from './components/HomePage.vue'
import Posts from './components/AllPosts.vue'
import Post from './components/SinglePost.vue'

export default {
  components: [
    Home,
    Posts,
    Post,
  ]
}

</script>

