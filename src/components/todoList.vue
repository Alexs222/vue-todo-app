<template lang="pug">
  .todo-list
    .content
      ul.list
        li.item(v-for="todo in todos")
            todo-item(
                :todo="todo"
                @removeTodo="removeTodo"
                @checkTodo="checkTodo"
            ) 
    .footer
      .footer-content
        .counter
          | Кол-во заданий: 0
        .filter
          button(type="button") all
          button(type="button") compleated
          button(type="button") active
</template>


<script>
import todoItem from './todoItem';
export default {
    components: {
        todoItem
    },
    props: {
        todos: Array
    },
    methods: {
        removeTodo(todoId) {
            this.$emit("removeTodo", todoId);
        },
        checkTodo(todo) {
            this.$emit("checkTodo", todo);
        }
    }
}
</script>

<style src="styles/todoList.scss" lang="scss" scoped></style>


