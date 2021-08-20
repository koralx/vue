<template>
  <post-form @create="createPost" />
  <post-list @remove="removePost" :posts="posts" />
</template>

<script>
import PostList from '@/components/PostList';
import PostForm from '@/components/PostForm';
export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'React', body: 'About post 1 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'},
        {id: 2, title: 'Js', body: 'About post 2 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'},
        {id: 3, title: 'Vue', body: 'About post 3 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'}
      ],
      body: "",
      title: ""
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(p=> p.id !== post.id)
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
