<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input
      v-model="post.title"
      class="input"
      type="text"
      placeholder="Название поста"
    />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Описание поста"
    />
    <button class="button" @click="createPost">Создать пост</button>
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
      this.$emit('create', this.post);
      this.post = {
        title: '',
        body: '',
      };
    },
  },
};
</script>

<style>
.input {
  border: 1px solid coral;
  width: 100%;
  padding: 10px;
  margin: 5px;
}
form {
  display: flex;
  flex-direction: column;
}
.button {
  border: 2px solid coral;
  padding: 10px;
  background-color: transparent;
  margin-top: 10px;
  align-self: flex-end;
}
</style>
