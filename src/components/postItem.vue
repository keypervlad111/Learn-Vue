<template>
  <div class="post">
        <div>
            <div><strong>Name:</strong>{{ post.title }}</div>
            <div><strong>Post body:</strong>{{ post.body}}</div>
        </div>
        <div class="post_btns">
            <my-button @click="$emit('remove', post)">Delete</my-button>
        </div>
    </div>
</template>

<script>
export default { 
    props: {
        post: {
            type: Object,
            required: true,
        }
    }
}
</script>

<style>
.post {
    padding: 15px;
    border: 2px solid black;
    margin-top: 15px;
    display: flex;
    justify-content: space-between;
}
</style>