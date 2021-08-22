<template>
   <div class="post">
      <div>
         <div>Название: {{post.title}}</div>
         <div>Описание: {{post.body}}</div>
      </div>
      <div style="align-self: flex-start;">
         <click-button @click="$emit('remove', post)">X</click-button>
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
  justify-content: space-between;
  align-items: flex-start; 

  width: 97vw;
  min-height: 200px;

  padding: 15px;
  margin: 2vh 1vw;

  border: 2px solid black;
  border-radius: 15px;
  
  font-size: 20px;
}
</style>