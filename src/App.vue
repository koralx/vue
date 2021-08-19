<template>
  <div>
    <post-form @create="createPost"/>
    <post-list :posts="posts"/>
  </div>
</template>

<script>
import PostList from '@/components/PostList';
import PostForm from './components/PostForm';

export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'React', body: 'About post 1'},
        {id: 2, title: 'Js', body: 'About post 2'},
        {id: 3, title: 'Vue', body: 'About post 3'}
      ],
      body: "",
      title: ""
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    }
  }
}
</script>

<style>
* {
  resize: none;
  font-weight: 500;
  font-size: 18px;
  font-family: 'Courier New', Courier, monospace;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
