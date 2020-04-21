<template>
    <div id="todo">
        <div v-for="todo in todos" v-bind:key="todo.id">
            <TodoItem v-bind:todo="todo" />
        </div>
    </div>
</template>

<script>
import TodoItem from '../components/TodoItem'

export default {
    name : "Todos",
    props : {
        todos : {
            type : Array,
            required : true,
        },
    },
    components:{
        TodoItem,
    }
}
</script>