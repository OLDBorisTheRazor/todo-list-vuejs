<template>
    <div>
        <ul>
            <TodoItem
                v-for="(todo, i) of todos"
                v-bind:todo="todo"
                v-bind:index="i"
                v-on:delete-todo="deleteTodo"
            />
        </ul>
    </div>
</template>

import TodoItem from "./components/Todoitem";
<script>
    import TodoItem from "./TodoItem";
    export default {
        name: "TodoList",
        props: ['todos'],
        components: {TodoItem},
        comments: {
            TodoItem
        },
        methods: {
            deleteTodo(id) {
                this.$emit('delete-todo', id)
            }
        }
    }
</script>

<style scoped>
    ul {
        list-style: none;
        padding: 0;
        margin: 0 20%;
    }
</style>