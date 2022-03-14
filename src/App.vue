<template>
  <div id="app">
    <h2>My todolist</h2>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>
<script>
import Todos from '../src/components/Todos.vue';
import AddTodo from '../src/components/AddTodo.vue';
export default {
  name: 'app',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Gör klart kunskapskontrollen',
          completed: false
        },
      ],
    }
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
}
</script>
<style>

h2{
  text-align: center;
  font-size: 2.5em;
}

body{
  background-image: linear-gradient(120deg, #eda7e7 0%, #8a8afe 100%);
}
</style>