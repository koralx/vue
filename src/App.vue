<template>
  <div class="header">
    <div class="app_btns">
      <click-button class="glass" @click="showDialog" >Создать пост</click-button>
        <h1>Список постов</h1>
      <select-list v-model="selectedSort" :options="sortOptions"/>
    </div>
  </div>

  <modal-dialog v-model:show="dialogVisible" >
    <post-form @create="createPost" />
  </modal-dialog>

  <post-list v-if="!nowLoading" @remove="removePost" :posts="posts" />
  <div style="display: flex; justify-content: center; width: 100vw;" v-else>
    Идёт загрузка..
  </div>



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
      nowLoading: false,
      selectedSort: '',
      sortOptions: [
        {value: 'title', name: 'По названию'},
        {value: 'body', name: 'По описанию'}
      ]
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
        this.nowLoading = true;
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
        this.posts = response.data;
      } catch (e) {
        alert('Ошибка')
      } finally {
        this.nowLoading = false;
      }
    }
  },
  mounted() {
    this.fecthPosts()
  }
}
</script>

<style>
@font-face {
  font-family: Sfpro;
  src: url('/fonts/SFProDisplay-Light.ttf');
}

h1 {
  font-size: 40px;
  text-align: center;
  color: white;
  text-shadow: 0px 0px 5px rgba(0,0,0, 0.8);
}

* {
  resize: none;
  font-family: 'Courier New', Courier, monospace;
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  font-family: Sfpro;
}
.header {
  margin: 0 1vw;
  margin-bottom: 3vh;

  padding: 1vh 1vw;
  background: rgba(255, 255, 255, 0.1);
  height: 55px;
  border-bottom-left-radius: 15px;
  border-bottom-right-radius: 15px;
}
.app_btns {
  display: flex;
  justify-content: space-between;
}
</style>
