<template>
  <div class="app">
    <h1>
      Страница с постами
    </h1>
    <my-button @click="showDialog" style="margin: 15px 0"
      >Создать пост</my-button
    >
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost"
    /></my-dialog>
    <post-list :posts="posts" @remove="removePost" />
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
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
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
.app {
  padding: 10px;
}
</style>
