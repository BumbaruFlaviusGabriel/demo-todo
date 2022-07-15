<script setup>
import TodoListItem from './TodoListItem.vue';
import {pushScopeId, ref} from 'vue';

const response = await fetch('https://jsonplaceholder.typicode.com/todos');
let todos = await response.json();
todos = todos.slice(0,5);
const reactiveTodos = ref(todos);
const text = ref(" ");

function handleTodoItemDeleted(todoItemId){
    console.log(`Item deleted: ${todoItemId}`);
    reactiveTodos.value=reactiveTodos.value.filter(item => item.id !== todoItemId);
    console.log(todos);
}

function handleSubmit(){

    const add = {
        completed:false,
        id:1,
        title:text.value,
        userId:1
    }

    
    todos.push(add)
}

function handleTodoItemCompleted(todoItemId,completed){
    console.log(`Item completed: ${todoItemId} >> ${completed}`);
}

</script>

<template>
    <form>
        <p>
            <input
            type="text" v-model="text"/>
        </p>

        <p>
            <button class="btn-add" @click="handleSubmit">Submit</button>
        </p>
    </form>
    
    <div class="todo-list">
        <TodoListItem
            v-for="todo of reactiveTodos"
            :key="todo.id"
            :id="todo.id"
            :title="todo.title"
            :completed="todo.completed"
            @todo-item-deleted="handleTodoItemDeleted(todo.id)"
            @todo-item-completed="completed => handleTodoItemCompleted(todo.id,completed)"
        />
    </div>
</template>

<style scoped>

.btn-add {
    background-color: rgba(255, 255, 255, 0.8);
    border: 3px solid rgba(0, 0, 0, 0.8);
    padding: 10px;
    font-size: px;
    text-align: center;
    cursor: pointer;
    justify-self: right;
    font-family: "Open Sans", sans-serif;
    letter-spacing: 3px;
    box-shadow: 1px 1px 0px 0px, 2px 2px 0px 0px, 3px 3px 0px 0px, 4px 4px 0px 0px, 5px 5px 0px 0px;
}

</style>