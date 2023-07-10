<template>
    <h5>Todo List</h5>
    <ul>
      <li v-for="todo in todos" v-bind:key="todo.id">
        {{ todo.text }}
        <button v-on:click="deleteTodo(todo.id)">DEL</button>
      </li>
    </ul>
   </template>
   
   <script>
   export default {
    props: ['todos'],
    emits: ['delete'],
    methods: {
      deleteTodo (id) {
        this.$emit('delete', id);
      }
    }
   }
   </script>