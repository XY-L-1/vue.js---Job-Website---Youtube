<script>
export default {
  data() {
    return {
      name: "Vue Study",
      status: "true",
      tasks: ['Task 1', 'Task 2', 'Task 3'],
      link: 'https://www.google.com',
    };
  },

  methods: {
    toggleStatus() {
      if (this.status === "true") {
        this.status = "pending";
      }
      else if (this.status === "pending") {
        this.status = "false";
      }
      else {
        this.status = "true";
      }
    },

  },

};
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'true'"> user is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>user is inactive</p>

  <h1>Tasks:</h1>
  <ul>
    <li v-for="task in tasks" :key="task"> {{ task }}</li>
  </ul>

  <a v-bind:href="link">Go to Google</a>

  <button v-on:click="toggleStatus">Toggle Status</button>
</template>

