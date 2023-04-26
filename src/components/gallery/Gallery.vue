<script>
import Photo from "./Photo.vue"
export default {components: {Photo}}
</script>

<template>
<div>
  <slot></slot>
</div>
</template>

<style scoped>
  div {
    display: flex;
    column-gap: 10px;
    justify-content: space-evenly;
  }
</style>