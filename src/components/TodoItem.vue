<template>
  <li>
    <span>
      <input type="checkbox" />
      <strong>{{ todo.id }}</strong>
      {{ todo.title }}
    </span>
    <button class="btn-remove">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
li {
  border: 1px solid lavender;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}

input {
  margin-right: 1rem;
}

.btn-remove {
  background: purple;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
}

.done {
  text-decoration: line-through;
}
</style>
