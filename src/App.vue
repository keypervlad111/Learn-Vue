<template>
<div class="app">
    <post-form @create="createPost"> </post-form>
    <post-list :posts="posts"> </post-list>
</div>
</template>

<script>
import postForm from "./components/postForm.vue";
import postList from "./components/postList.vue"
export default {
    components: { postForm, postList },
    data() {
        return{
            posts: [
                {id: 1, title: "Jestem z Faceboock'a", body: "Opisuje bardzo dobrze cos"},
                {id: 2, title: "Jestem z Tiktok'a", body: "Opisuje bardzo dobrze cos 2"},
                {id: 3, title: "Jestem z Insta", body: "Opisuje bardzo dobrze cos 3"}
            ],
        }
    },
    methods: {
        createPost(post){
            this.posts.push(post);
        },
    }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app{
    padding: 20px;
}
</style>
