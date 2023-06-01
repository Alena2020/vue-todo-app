<template>
  <div>
      <transition-group name="post-list" tag="ul">
          <TodoItem
          v-for="(todo, i) of todos"
          v-bind:todo="todo"
          v-bind:index="i"
          v-on:remove-todo="removeTodo"
        />
      </transition-group>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.post-list-item {
  display: inline-block;
  margin-right: 10px;
}
.post-list-enter-active, .post-list-leave-active {
  transition: all 0.6s;
}
.post-list-enter, .post-list-leave-to  {
  opacity: 0;
  transform: translateY(150px);
}
.post-list-move {
  transition: transform 0.6s;
}
</style>
