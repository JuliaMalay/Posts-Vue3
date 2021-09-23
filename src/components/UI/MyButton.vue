<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button',
};
</script>

<style>
.button {
  border: 1px solid #4169e1;
  padding: 10px;
  background-color: transparent;
}
</style>
