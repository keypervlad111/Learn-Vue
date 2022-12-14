<template>
  <form @submit.prevent>
        <h4>Zrob swoj post:</h4>
        <my-input
        v-model="post.title"
        placeholder="Title" />
        <my-input
        v-model="post.body"
        placeholder="Body" />
        <my-button
        style="align-self: flex-end; margin-top: 15px;" 
        @click="createPost">
        Post</my-button>
    </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style>
form {
  display: flex;
  flex-direction: column;
}
</style>