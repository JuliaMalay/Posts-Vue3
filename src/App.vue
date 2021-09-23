<template>
  <div>
    <post-form @create="createPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostForm from '@/components/PostForm';
import PostList from '@/components/PostList';

export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'JS1', body: 'JavaScript1'},
        {id: 2, title: 'JS2', body: 'JavaScript2'},
        {id: 3, title: 'JS3', body: 'JavaScript3'},
        {
          id: 4,
          title: 'Пост о булочке синнабон',
          body: 'Синнабон-булочка с корицей',
        },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
