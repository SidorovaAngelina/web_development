<template>
    <li :class="{ completed: todo.completed }">
      <input 
        type="checkbox" 
        :checked="todo.completed" 
        @change="$emit('complete-todo', index)" 
      />
      {{ todo.text }}
      <button @click="$emit('delete-todo', index)" class="delete-button">Удалить</button>
    </li>
</template>

<script>
export default {
    props: ['todo', 'index']
}
</script>

<style scoped>
li {
    margin-bottom: 10px;
}
.completed {
    text-decoration: line-through;
    color: green;
    background-color: #d4edda;
}
button {
    margin-left: 10px;
    padding: 8px 12px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
}
.delete-button {
    background-color: #ff4c5b;
    color: white;
}
.delete-button:hover {
    background-color: #ff192d;
}
</style>
