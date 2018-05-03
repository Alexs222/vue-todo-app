<template lang="pug">
    .todo
        pre {{todos}}
        todo-input(
            @addTodo="addTodo"
        )
        todo-list
</template>


<script>
import todoInput from "./todoInput";
import todoList from "./todoList";

export default {
    components: {
        todoInput, todoList
    },
    data() {
        return {
            todos: []
        }
    },
    methods: {
        addTodo(todo) {
            this.todos.push(todo);
        }
    }

}
</script>

<style lang="scss" src="styles/todo.scss">

</style>


