<template>
    <div>
        <h2>List users</h2>
        <post-item v-for="post in posts" :post="post"></post-item>
    </div>
</template>

<script>
import postItem from './postItem.vue'
export default {
  components: { postItem },
    props: {
        posts: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style scoped>

</style>