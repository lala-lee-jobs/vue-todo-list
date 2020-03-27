<script>
import TodoInput from './TodoInput';
import TodoItem from './TodoItem';

export default {
  components: {
    TodoInput,
    TodoItem
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    addTodo(text) {
      this.todos.push(text);
    },
    removeTodo(idx) {
      this.todos.splice(idx, 1);
    }
  }
}
</script>

<template>
  <div>
    <TodoInput @submit="addTodo"/>
    <ul>
      <TodoItem 
        v-for="(todo, idx) in todos" 
        :data="todo"
        @click.native="removeTodo(idx)" />
    </ul>
  </div>
</template>

<style>
  
</style>