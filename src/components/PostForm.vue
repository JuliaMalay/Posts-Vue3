<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <my-input v-model="post.title" placeholder="Название поста" />
    <my-input v-model="post.body" placeholder="Описание поста" />
    <my-button class="btn" @click="createPost">Создать пост</my-button>
  </form></template
>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      if (this.post.title && this.post.body) {
        this.$emit('create', this.post);
        this.post = {
          title: '',
          body: '',
        };
      } else {
        alert('Заполните поля!');
      }
    },
  },
};
</script>

<style>
form {
  display: flex;
  flex-direction: column;
}
.btn {
  align-self: flex-end;
  margin-top: 10px;
}
</style>
