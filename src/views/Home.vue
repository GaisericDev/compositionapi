<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">Toggle posts</button>
    <button @click="posts.pop()">Delete a post</button>
  </div>
</template>

<script>
import { ref } from "vue";
import PostList from "../components/PostList.vue";

export default {
  name: "Home",
  components: { PostList },
  setup() {
    const posts = ref([
      { title: "Welcome to the blog", body: "Lorem ipsum", id: 1 },
      { title: "Top 5 css tips", body: "Lorem ipsum", id: 2 },
    ]);
    const showPosts = ref(true);
    return { posts, showPosts };
  },
};
</script>
