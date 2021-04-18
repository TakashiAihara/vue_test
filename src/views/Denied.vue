<template>
  <ul>
    <li v-for="todo in todos" v-bind:key="todo.id">
      {{ todo.text }}
      <button @click="deleteTodo(todo.id)">x</button>
      <button @click="addTodo()">◯</button>
    </li>
  </ul>
</template>

<script lang="ts">
export default {
  data() {
    return {
      todos: [
        { id: '1', text: 'todo1' },
        { id: '2', text: 'todo2' },
        { id: '3', text: 'todo3' },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addTodo() {
      this.todos.push(
        {
          id: Math.max(...this.todos.map((e) => parseInt(e.id, 10))) + 1,
          text: `todo${Math.max(...this.todos.map((e) => parseInt(e.id, 10))) + 1}`,
        },
      );
    },
  },
};
</script>
