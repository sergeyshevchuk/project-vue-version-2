<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox" v-on:change="todo.completed = !todo.completed">
                   <strong>{{todo.id}}</strong>
            {{todo.title}}
        </span>
        <button class="rm" v-on:click="$emit('remove-todo', todo.id)"
        >&times;</button>
    </li>
</template>

<script>
    export default {
        props: {
            todo: {
                type: Object,
                required: true
            }
        }
    }
</script>

<style>
    li {
        border: 1px solid darkcyan;
        display: flex;
        justify-content: space-between;
        padding: .2rem 1rem;
        margin-bottom: 1rem;
    }

    .rm {
        background: red ;
        color: #fff;
        border-radius: 50%;
        font-weight: lighter;
    }
    input {
        margin-right: 1rem;
    }
    .done {
        text-decoration: line-through;
    }
</style>
