<template>
    <div class="todo-list">
        <h1 class="title">Список моих дел</h1>
        <AddNewTodo @add-todo="addNewTodo" />
        <ul>
            <TodoItem
                v-for="(todo, index) in todos"
                :key="index"
                :todo="todo"
                :index="index"
                @delete-todo="deleteTodo"
                @complete-todo="completeTodo"
            />
        </ul>
    </div>
</template>

<script>
import AddNewTodo from './components/AddNewTodo.vue'
import TodoItem from './components/TodoItem.vue'

export default {
    components: { AddNewTodo, TodoItem },
    data() {
        return {
            todos: []
        }
    },
    methods: {
        addNewTodo(todo) {
            this.todos.push({
                text: todo,
                completed: false
            })
        },
        deleteTodo(index) {
            this.todos.splice(index, 1)
        },
        completeTodo(index) {
            this.todos[index].completed = !this.todos[index].completed;
        }
    }
}
</script>

<style scoped>
.todo-list {
    text-align: center;
}
.title {
    margin-bottom: 20px;
}
ul {
    list-style-type: none;
    padding: 0;
}
</style>
