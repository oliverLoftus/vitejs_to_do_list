<!-- src/components/AddToDo.vue -->
<template>
    <div>
        <h2>Add ToDo</h2>
        <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Enter a new ToDo" />
        <button @click="addTodo">Add</button>
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    setup(props, context) {
        const newTodo = ref('');
        const addTodo = () => {
            if (newTodo.value.trim() === '') return;
            context.emit('add-todo', newTodo.value);
            newTodo.value = '';
        };

        return {
            newTodo,
            addTodo,
        };
    },
};
</script>
