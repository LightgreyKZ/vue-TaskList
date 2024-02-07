<template>
    <!-- Реализуйте функционал добавления новой задачи в список. Создайте
    компонент "TaskForm", который будет содержать поля ввода для заголовка и
    описания задачи. -->
    <input type="text" v-model="taskName" placeholder="Task head">
    <input type="text" v-model="taskDesc" placeholder="Description">
    <button type="button" @click="Add">Add New Task</button>

  </template>
  
  
  <script>
  export default {
    data() {
      return {
        taskName: '',
        taskDesc: ''
      }
    },
    methods: {
        Add() {
            this.$emit('add', this.taskName, this.taskDesc)
        }
    }
  }
   
  </script>
  
  <style scoped>
  
  .redcolor {
    color: red;
  }
  
  input {
    display: block;
    margin-bottom: 10px;
    font-size: 20px;
    height: 40px;
    padding: 5px;
    border: 1px solid rgba(128, 128, 128, 0.514);
    border-radius: 5px;
    outline: none;
    background: rgba(128, 128, 128, 0.384);
  }
  
  button[type="button"] {
    border: 0;
    border-radius: 5px;
    outline: none;
    padding: 10px 15px;
    background-color: #47e24c;
    color: #154716;
    font-weight: bold;
    transition: all 0.5s ease;
  }
  
  button[type="button"]:hover {
    transform: translateY(5px);
    background-color: rgb(228, 59, 59);
    border: 1px solid rgb(107, 0, 105);
  }
  
  </style>
  