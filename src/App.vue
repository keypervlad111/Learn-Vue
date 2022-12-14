<template>
  <div class="app">
    <h1>Site with posts</h1>
    <input type="text" v-model="modificationValue">
    <my-button @click="showDialog" style="margin: 15px 0">
      Create new Post
    </my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost"> </post-form>
    </my-dialog>
    <post-list :posts="posts" @remove="removePost"> </post-list>
  </div>
</template>

<script>
// import MyDialog from './UI/MyDialog.vue'; i dont need, because i make UI/index.js
//  --->components: { MyDialog },
import postForm from "./components/postForm.vue";
import postList from "./components/postList.vue";
export default {
  components: { postForm, postList },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Jestem z Faceboock'a",
          body: "Opisuje bardzo dobrze cos",
        },
        {
          id: 2,
          title: "Jestem z Tiktok'a",
          body: "Opisuje bardzo dobrze cos 2",
        },
        { id: 3, title: "Jestem z Insta", body: "Opisuje bardzo dobrze cos 3" },
      ],
      dialogVisible: false,
      modificationValue: ''
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>
