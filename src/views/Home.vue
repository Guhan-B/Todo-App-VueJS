<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"></AddTodo>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo,
  },
  data(){
    return {
      todos : [],
      count: 0,
    }
  },
  methods : {
    addTodo(todoTask){
      this.todos.push({id:this.count,task:todoTask,completed:false});
      this.count+=1;
    },
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
    }
  }

}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
