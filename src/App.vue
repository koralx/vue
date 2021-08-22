<template>
  <div style="margin: 15px 0">
    <click-button @click="fecthPosts" >Получить посты</click-button>
    <h1>Список постов</h1>
    <click-button @click="showDialog" >Создать пост</click-button>
  </div>
  <modal-dialog v-model:show="dialogVisible" >
    <post-form @create="createPost" />
  </modal-dialog>
  <post-list @remove="removePost" :posts="posts" />
</template>

<script>
import PostList from '@/components/PostList';
import PostForm from '@/components/PostForm';
import axios from 'axios'
export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [],
      dialogVisible: false,
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter(p=> p.id !== post.id)
    },
    showDialog(){
      this.dialogVisible = true;
    },
    async fecthPosts() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
        this.posts = response.data;
      } catch (e) {
        alert('Ошибка')
      }
    }
  }
}
</script>

<style>
* {
  resize: none;
  font-family: 'Courier New', Courier, monospace;
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
#app {
 margin: 15px;
}
</style>
