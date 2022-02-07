<template>
  <div class="post-list"></div>
  <div v-for="post in posts" :key="post.id">
    <SinglePost :post="post" />
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from "@vue/runtime-core";
import SinglePost from "./SinglePost.vue";

export default {
  components: { SinglePost },
  props: ["posts"],
  setup(props) {
    onMounted(() => {
      console.log("Mounted");
    });
    onUnmounted(() => {
      console.log("Component unmounted");
    });
    onUpdated(() => {
      console.log("Component updated");
    });
  },
};
</script>

<style>
</style>