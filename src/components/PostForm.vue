<template>
    <form @submit.prevent >
      <h4>Создание поста</h4>
      <text-input 
        v-model="post.title"
        class="input-title" 
        type="text" 
        placeholder="Название"/>
      <textarea 
        v-model="post.body"
        class="input-body" 
        placeholder="Описание"></textarea>
      <click-button style="margin-top: 15px; align-self: flex-end;" @click="createPost">Создать</click-button>
    </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: ''
      } 
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        body: '',
        title: ''
      }
    }
  }
}
</script>

<style>

form {
  display: flex;
  flex-direction: column;
  border-radius: 5px;
  border: 2px solid black;
  padding: 15px;
  margin: 15px;
  width: 500px;
}

.input-body {
  outline: none;
  height: 100px;
  border: 0px;
  border-top: 1px black solid;
  border-left: 1px black solid;
  padding: 5px;
}

</style>