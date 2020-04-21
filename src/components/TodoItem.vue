<template>
    <div class="todo-item" v-bind:class="{'completed' : todo.completed}">
        <p>{{ todo.task }}</p>
        <input type="checkbox" v-on:change="todo.completed=!todo.completed">       
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
        toggleStatus(){
            this.todo.completed = !this.todo.completed;
        }
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
.completed{
    text-decoration: line-through;
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
}
</style>