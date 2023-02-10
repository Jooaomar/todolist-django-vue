<template>
    <div>
      <form @submit.prevent="createTask">
        <div>
          <label for="title">Title:</label>
          <input id="title" v-model="task.title" />
        </div>
        <div>
          <label for="description">Description:</label>
          <textarea id="description" v-model="task.description"></textarea>
        </div>
        <button type="submit">Create Task</button>
      </form>

      <div>
        <h1>Lista de Tarefas</h1>
        <ul>
          <li v-for="task in tasks" :key="task.id">{{ task.title }}</li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        tasks: [],
        task: {
          title: '',
          description: ''
        }
      };
    },
    methods: {
      async createTask() {
        try {
          await axios.post('http://localhost:8000/api/tasks/', this.task);
          // this.task = { title: '', description: '' };
          await axios.get("http://127.0.0.1:8000/api/tasks/")
            .then(resposse =>(this.tasks = resposse.data))
        } catch (error) {
          console.error(error);
        }
      }
    }
  };
  </script>
  