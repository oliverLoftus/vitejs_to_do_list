<!-- src/components/ToDoList.vue -->
<template>
  <div>
    <h1>ToDo list</h1>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{todo}}
        <button @click="removeTodo(index)">Remove</button>
      </li>
     </ul>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  props: {
    todos: Array, // Define a prop called "todos" as an array
  },
  methods: {
    removeTodo(index) {
        this.$emit('remove-todo', index); // Emit a custom event to remove a ToDo
    },
  },
};
</script>
