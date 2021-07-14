<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox"
                   v-on:change="todo.completed = !todo.completed">
            <strong>{{ index + 1 }}</strong>
            {{ todo.title | uppercase}}
        </span>
        <button class="del"
            v-on:click="$emit('delete-todo', todo.id)"
        >&times;</button>
    </li>

</template>

<script>
    export default {
        name: "Todoitem",
        props:
            {
            todo:
                {
                type: Object,
                required: true
                },
            index: Number
            },
        filters: {
            uppercase(value) {
                return value.toUpperCase()
            }
        }
    }
</script>

<style scoped>
    li {
        border: 1px solid #ccc;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }
    .del {
        background: #e01111;
        border-radius: 50%;
        color: #2a250b;
        box-shadow: none;
        cursor: pointer;
    }
    .done {
        text-decoration: line-through;
    }
    input {
        margin-right: 1rem;
    }
</style>