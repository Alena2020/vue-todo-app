<template>
  <div id="app">
    <h1>Todo application</h1>
    <AddTodo @add-todo="addTodo" />
    <hr />
    <TodoList v-bind:todos="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import AddTodo from "@/components/AddTodo";
export default {
  name: "app",
  data() {
    return {
      todos: [],
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=7")
      .then((response) => response.json())
      .then((json) => {
        this.todos = json;
      });
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
    },
  },
  components: {
    TodoList,
    AddTodo,
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
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
