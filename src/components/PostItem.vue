<template>
   <div class="post">
      <div>
         <div>Название: {{post.title}}</div>
         <div>Описание: {{post.body}}</div>
      </div>
      <div class="heu">
         <click-button >Удалить</click-button>
      </div>
   </div>
</template>

<script>
import clickButton from './UI/clickButton.vue'
export default {
  components: { clickButton },
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
  width: 50%;
  height: 100px;
  padding: 15px;
  margin: 15px;
  border: 2px solid black;
  border-radius: 5px;
  justify-content: space-between;
}
.heu {

   align-self: center;
}
</style>