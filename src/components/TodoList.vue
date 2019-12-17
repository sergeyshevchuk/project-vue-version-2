<template>
    <div>
        <ul>
          <Todoitem
                  v-for = "todo in todos" :key="todo"
          v-bind:todo="todo"
                  v-on:remove-todo="removeTodo"
          />
        </ul>
    </div>
</template>

<script>
    import Todoitem from '@/components/Todoitem'
    export default {
        props: ['todos'],
        components: {
            Todoitem
        },
        methods : {
            removeTodo(id) {
        this.$emit('remove-todo', id)           }
        }
    }
</script>

<style scoped>
    ul {
        list-style: 0;
        margin: 0;
        padding: 0;
    }
</style>