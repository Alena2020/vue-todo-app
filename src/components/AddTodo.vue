<template>
  <from @submit.prevent="onSubmit">
    <input type="text" />
    <button type="submit">Create</button>
  </from>
</template>

<script>
export default {
  methods: {
    onSubmit() {},
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input {
  width: 400px;
  margin: 0 5px;
}
</style>
