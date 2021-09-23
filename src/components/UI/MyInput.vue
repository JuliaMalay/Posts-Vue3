<template>
  <input :value="modelValue" @input="updateInput" class="input" type="text" />
</template>

<script>
export default {
  name: 'my-input',
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value);
    },
  },
};
</script>

<style>
.input {
  border: 1px solid #4169e1;
  width: 100%;
  padding: 10px;
  margin-top: 5px;
}
</style>
