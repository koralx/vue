<template>
    <div class="post" v-for="post in posts" :key="post.id" >
      <div>Название: {{post.title}}</div>
      <div>Описание: {{post.body}}</div>
    </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style>
.post {
  display: block;
  width: 50%;
  height: 100px;
  padding: 15px;
  margin: 15px;
  border: 2px solid black;
  border-radius: 5px;
}
</style>