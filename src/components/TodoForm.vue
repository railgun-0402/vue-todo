<template>   
    <h3>My Todo</h3>
    <input v-model="newTodo" placeholder="Input here...">
    <button v-on:click="addTodo">ADD</button>
</template>

<script>
export default {
 data () {
   return {
     newTodo: ''
   }
 },
 emits: ['add'],
 methods: {
   addTodo () {
     if (this.newTodo === '') return;
     this.$emit('add', this.newTodo);
     this.newTodo = '';
   }
 }
}
</script>