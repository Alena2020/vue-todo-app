<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button class="btn" type="submit">Create</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false,
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      }
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  margin-top: 10px;
}

input {
  width: 500px;
  margin: 0 5px;  
  border-radius: 25px;
  padding: 1px 15px;
}

.btn {
  padding: 5px 15px;
  background: #2ba7dd;
  color: mediumblue;
  border: 2px solid #2ba7dd; 
  border-radius: 25px;
  cursor: pointer;
}

.btn:hover {
  background: mediumpurple;
  box-shadow: 2px 2px 2px aqua, inset -1px 10px 10px midnightblue;
  color: white;
}
</style>
