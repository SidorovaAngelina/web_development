<template>
    <div>
      <input 
        type="text" 
        v-model="newTodo" 
        placeholder="Добавить новое дело" 
        class="todo-input"
      >
      <button @click="addNewTodo" class="add-button">Добавить</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTodo: ''
      }
    },
    methods: {
      addNewTodo() {
        if (this.newTodo.trim()) {
          this.$emit('add-todo', this.newTodo)
          this.newTodo = ''
        }
      }
    }
  }
  </script>
  
  <style scoped>
  .todo-input {
    width: 300px;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
    margin-right: 10px;
  }
  
  .add-button {
    padding: 8px 12px;
    background-color: #FF69B4; 
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .add-button:hover {
    background-color: #FF99CC;
  }
  </style>
  