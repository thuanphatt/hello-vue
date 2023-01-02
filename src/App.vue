<template>
  <input type="text" v-model="newTask" />
  <button @click="addTask()">Add</button>
  <div v-for="todo in todos" :key="todo">
    <input type="checkbox" v-model="todo.done" />
    <span :class="{ done: todo.done }"> {{ todo.task }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      newTask: "",
      todos: [],
    };
  },
  methods: {
    addTask: function () {
      this.todos.push({ task: this.newTask, done: false });
    },
  },
};
</script>

<style>
.done {
  text-decoration: line-through;
}
</style>
