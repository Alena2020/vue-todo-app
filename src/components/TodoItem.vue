<template>
  <li>
    <span v-bind:class="{ done: todo.completed }">
      <input type="checkbox" v-model="todo.completed" />
      <strong>{{ index + 1 }}</strong>
      {{ todo.title }}
    </span>
    <button class="btn-remove" v-on:click="$emit('remove-todo', todo.id)">
      &times;
    </button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: Number,
  },
};
</script>

<style scoped>
li {
  border: 1px solid lavender;
  border-radius: 25px;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}

input {
  margin-right: 1rem;
}

.btn-remove {
  background: mediumorchid;
  box-shadow: 2px 2px 2px aqua, inset 2px 3px 5px midnightblue;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
  margin-left: 1rem;
  padding: 1px 4px;
}

.done {
  text-decoration: line-through;
}
</style>
