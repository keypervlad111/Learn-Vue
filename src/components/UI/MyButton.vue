<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
    name: 'my-button',
}
</script>

<style>
.btn {
    /* margin-top: 15px; */
    padding: 10px 15px;
    background: none;
    color: black;
    border: 1px solid black;
}
.btn:hover {
    border-radius: 10px;
    background: rgb(0, 0, 0);
    color: white;
    border: 1px solid white;
}
</style>