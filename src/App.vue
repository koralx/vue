<template>
  <div>
    <form action="">
      <h4>Создание поста</h4>
      <input class="input" type="text" placeholder="Название">
      <input class="input" type="text" placeholder="Описание">
      <button class="btn" @click="createPost">Создать</button>
    </form>
    <div class="post" v-for="post in posts" :key="post.id" >
      <div>Название: {{post.title}}</div>
      <div>Описание: {{post.body}}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'React', body: 'About post 1'},
        {id: 2, title: 'Js', body: 'About post 2'},
        {id: 3, title: 'Vue', body: 'About post 3'}
      ]
    }
  },
  methods: { 
  }
}
</script>

<style>
* {
  font-weight: 500;
  font-size: 18px;
  font-family: 'Courier New', Courier, monospace;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  display: block;
  width: 20%;
  height: 250px;
  padding: 25px;
  margin: 15px;
  border: 1px solid grey;
  border-radius: 15px;
}

</style>
