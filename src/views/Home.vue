<template>
  <div class="home">
    <h1>Home</h1>
    <button @click="showPosts = !showPosts">Toggle posts</button>
    <button @click="posts.pop()">Delete a post</button>
    <div class="error" v-if="error">{{ error }}</div>
    <div class="post-list" v-if="posts.length">
      <PostList v-if="showPosts" :posts="posts" />
    </div>
    <div class="loading" v-else>Loading...</div>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import getPosts from "../composables/getPosts";

export default {
  name: "Home",
  components: { PostList },
  //setup hook
  setup() {
    const { posts, error, showPosts, load } = getPosts();
    load();
    return { posts, showPosts, error };
  },
};
</script>
