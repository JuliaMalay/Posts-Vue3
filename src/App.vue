<template>
  <div>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong></div>
      <div><strong>Описание:</strong></div>
    </div>
  </div>
</template>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.post {
  padding: 15px;
  border: 2px solid rgba(255, 203, 33, 0.747);
  margin-top: 10px;
}
</style>
<script>
export default {
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
  methods: {},
};
</script>
