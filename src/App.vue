<template>
  <todo-form v-on:add="addTodo"></todo-form>
  <todo-list v-bind:todos="todos" v-on:delete="deleteTodo"></todo-list>
</template>

<script>
import TodoForm from './components/TodoForm';
import TodoList from './components/TodoList';

let nextId = 0;

export default {
  data () {
    return {
      todos: []
    }
  },  
  components: {
    TodoForm,
    TodoList
  },
  methods: {
    addTodo (newTodo) {
      nextId = nextId + 1;
      this.todos = [...this.todos, {id: nextId, text: newTodo}];
    },
    deleteTodo (id) {
     this.todos = this.todos.filter(todo => todo.id !== id);
   }
  }
}
</script>

