<template>
  <div id="app">
    <Header></Header>
    <AddTodo v-on:add-todo="addTodo"></AddTodo>
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import Header from "./components/Header";

export default {
  name: 'App',
  components: {
    Todos,
    AddTodo,
    Header,
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
