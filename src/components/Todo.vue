<template>
  <div v-bind:class="{ 'completed': todo.completed }">
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <button @click="$emit('delete-todo', todo.id)">Delete</button>
  </div>
</template>
<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>
<style scoped>

  .completed {
    text-decoration: line-through;
  }

  button{
    font-size: 0.7em;
    width: 15%;
    border-radius: 5px;
    border: 2px solid white;
    color: #9932ff;
    border: 2px solid #9932ff;
  }

  button:hover{
    color: white;
    background-color: #9932ff;
  }

</style>