<template>
   <div class="post">
      <div>
         <div>Название: {{post.title}}</div>
         <div>Описание: {{post.body}}</div>
      </div>
      <div style="align-self: center;">
         <click-button >Удалить</click-button>
      </div>
   </div>
</template>

<script>
export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
.post {
  display: flex;
  width: 100%;
  height: 150px;
  padding: 15px;
  margin: 15px;
  border: 2px solid black;
  border-radius: 5px;
  justify-content: space-between;
}
</style>