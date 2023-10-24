<!-- src/App.vue -->
<template>
  <div>
    <h1>Vue 3 ToDo App</h1>
    <add-todo @add-todo="addTodo" />
    <to-do-list :todos="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>
import AddTodo from './components/AddToDo.vue';
import ToDoList from './components/ToDoList.vue';
import { ref } from 'vue';

export default {
  components: {
    AddTodo,
    ToDoList,
  },
  setup() {
    const todos = ref([]);

 

    const addTodo = (newTodo) => {
      console.log('Adding:', newTodo);
      todos.value.push(newTodo);
    };

    const removeTodo = (index) => {
      todos.value.splice(index, 1);
    };

    return {
      todos,
      addTodo,
      removeTodo,
    };
  },
};
</script>
