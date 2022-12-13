<template>
  <form @submit.prevent>
        <h4>Zrob swoj post:</h4>
        <input 
        v-model="post.title"
        type="text" 
        class="inputs" 
        placeholder="Title">
        <input 
        v-model="post.body"
        type="text" 
        class="inputs" 
        placeholder="Body">
        <my-button
        style="align-self: flex-end; margin-top: 15px;" 
        @click="createPost">
        Post</my-button>
    </form>
</template>

<script>
export default {
    data(){
        return {
            post: {
                title: '',
                body: ''
            },
        }
    },
    methods: {
        createPost(){
            this.post.id = Date.now();
            this.$emit('create', this.post);
            this.post = {
                title: '',
                body: ''
            }
        },
    }
}
</script>

<style>
form {
    display: flex;
    flex-direction: column;
}
.inputs {
    width: 100%;
    border: 1px solid black;
    padding: 10px 15px;
    margin-top: 15px;
}
</style>