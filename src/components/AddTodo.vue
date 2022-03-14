<template>
  <div>
<form @submit="addTodo">
    <input type="text" v-model="title" name="title">
    <button type="submit">Add</button>
</form>
  </div>
</template>
<script>
import { v4 as uuidv4 } from 'uuid';
uuidv4();
export default {
  name: 'AddTodo',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }
      console.log(newTodoObj);
      this.$emit('add-todo', newTodoObj);
      this.title = '';
    }
  }
}
</script>
<style scoped>

input{
  width: 20%;
  padding: 5px;
  border-radius: 5px;
  border: 2px solid #9932ff;
}

form{
  display: flex;
  justify-content: center;
  margin-left: auto;
  margin-right: auto;
}

button{
  font-size: 1em;
  width: 5%;
  border-radius: 5px;
  border: 2px solid #9932ff;
  color: #9932ff;
}

button:hover{
    color: white;
    background-color: #9932ff;
  }

</style>