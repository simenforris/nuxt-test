<template>
  <div v-if="this.posts">
    <h1>Posts</h1>
    <main>
      <div v-for="(post) in posts" :key="post.id">
        <h2>{{ post.title }}</h2>
        <p>{{ post.body }}</p>
      </div>
    </main>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

interface Post {
  userId: number;
  id: number;
  title: string;
  body: string;
}

export default Vue.extend({
  name: 'PostsPage',
  data() {
    const posts: Post[] | null = null;
    return {
      posts
    }
  },
  async fetch() {
    try {
      const response = await this.$axios.get('https://jsonplaceholder.typicode.com/posts');
      this.posts = response.data;
    } catch (e) {
      this.posts = null;
    }
  }
})
</script>
