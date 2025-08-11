<script setup>
import { ref } from 'vue';

  const name = ref("Vue Study");
  const status = ref("true");
  const tasks = ref(['Task 1', 'Task 2', 'Task 3']);
  const newTask = ref('');
  
  const toggleStatus = () => {
    if (status.value === "true") {
      status.value = "pending";
    } else if (status.value === "pending") {
      status.value = "false";
    } else {
      status.value = "true";
    }
  };

  const addTask = () => {
    if (newTask.value.trim() !== '') {
      tasks.value.push(newTask.value);
      newTask.value = '';
    }
  }

  const deleteTask = (index) => {
    tasks.value.splice(index, 1);
  }

</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'true'"> user is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>user is inactive</p>

  <h1>Tasks:</h1>
  <ul>
    <li v-for="(task, index) in tasks" :key="task"> 
      <span>{{ task }}</span>
      <button v-on:click="deleteTask(index)">Delete</button>
    </li>
  </ul>

  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask" />
    <button type="submit">✅Submit</button>
  </form>

  <button v-on:click="toggleStatus">Toggle Status</button>
</template>

