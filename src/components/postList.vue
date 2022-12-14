<template>
  <div v-if="posts.length > 0">
    <h2>List users</h2>
    <post-item
    v-for="post in posts" 
    :key="post.id"
    :post="post"
    @remove = "$emit('remove', post)"
    ></post-item>
  </div>
  <h2 v-else class="no_post">No Posts</h2> 
  <!-- v-show instead v-if, but its no removed from DOM -->
</template>

<script>
import postItem from "./postItem.vue";
export default {
  components: { postItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.no_post{
    font-size: 100;
    background: #cecece;
    text-align: center;
    border-radius: 50px;
}
</style>