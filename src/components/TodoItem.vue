<template>
    <div class="todo-item" v-bind:class="{'completed' : todo.completed}">
        <p>{{ todo.task }}</p>
        <div class="controls">
            <input type="checkbox" v-on:change="todo.completed=!todo.completed">      
            <button v-on:click="$emit('del-todo',todo.id)"><font-awesome-icon :icon="['fas', 'trash-alt']" /></button> 
        </div>
    </div>
</template>

<script>
export default {
    name: 'TodoItem',
    props: {
        todo : {
            type: Object,
            required: true,
        },
    },
    methods: {

    }
}
</script>

<style scoped>
.todo-item{
    padding: 1rem;
    text-align: center;
    background-color: #95afc0;
    color: #fff;
    max-width: 550px;
    margin: 1rem auto;
    border: none;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.controls{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.completed{
    text-decoration: line-through;
}

button{
    background: none;
    color: #fff;
    border: none;
    font-size: 1.15rem;
    margin: 0 1rem;
    cursor: pointer;
}
.todo-item p{
    font-size: 1.25rem;
    letter-spacing: 1px;
    text-transform: capitalize;
    font-weight: bold;
}
.todo-item input[type="checkbox"]{
    width: 20px;
    height: 20px;
    margin: 0 1rem;
    background: #f4f4ff;
}
</style>