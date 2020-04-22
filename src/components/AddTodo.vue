<template>
    <div>
        <form v-on:submit.prevent>
            <input type="text" class="text" v-model="enteredTodo" v-on:keyup.enter="AddTodo">
            <input type="button" value="add" class="btn" v-on:click="AddTodo" >
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    props: {

    },
    data(){
        return {
            enteredTodo : ""
        }
    },
    methods : {
        AddTodo(){
            if(this.enteredTodo!=""){
                this.$emit('add-todo',this.enteredTodo);
                this.enteredTodo = "";
            }
        }
    }
    
}
</script>

<style scoped>
form{
    width: 800px;
    margin: 2rem auto;
    text-align: center;
}

input.text{
    width: 60%;
    padding: 0.45rem;
    font-size: 1rem;
    font-weight: 300;
    border: 1px rgba(153, 153, 153,0.7) solid;
    border-radius: 4px;
    transition: all 0.1s ease;
}

input.text:focus{
    outline: none;
    border-color: #5fa8d3;
    box-shadow: 0 0 3px #5fa8d3;
}

.btn{
    padding: 0.55rem 1.45rem;
    border: none;
    background: #95afc0;
    color: white;
    border-radius: 5px;
    margin: 0 1rem;
    font-size: 1rem;
    text-transform: uppercase;
    transition: all 0.2s ease;
}

.btn:hover{
    background-color: rgb(0, 113, 179) ;
}
</style>