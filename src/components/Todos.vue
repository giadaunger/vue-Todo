<template>
  <div>
    <ul>
      <li v-bind:key="todo.id" v-for="todo in todos">
        <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
      </li>
    </ul>
  </div>
</template>
<script>
import Todo from '../components/Todo.vue';
export default {
  name: 'Todos',
  components: {
    Todo
  },
  props: [
    "todos"
  ]
}
</script>
<style scoped>

ul{
  max-width: 50ch;
  text-align: center;
  padding: 10px;
  list-style: none;
  font-size: 1.5em;
  justify-content: center;
  margin-left: auto;
  margin-right: auto;
  border-radius: 5px;
}

li{
  margin-bottom: 30px;
  background-color: #98a0ff;
  padding: 10px;
  border-radius: 10px;
  border: 5px dotted #606dff;
}

li:nth-child(2n) {
  background-color: #f690ff;
  border: 5px dotted #f760ff;
}

</style>