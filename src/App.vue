<template>
  <div id="app">
    <h1>Todo application</h1>
    <hr />
    <TodoList v-bind:todos="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: 1, title: "Todo item 1", completed: false },
        { id: 2, title: "Todo item 2", completed: false },
        { id: 3, title: "Todo item 3", completed: false },
      ],
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
  },
  components: {
    TodoList,
  },
};
</script>

<style>
body {
  background: linear-gradient(90deg, #0dcaf0 0%, lavender 100%);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
