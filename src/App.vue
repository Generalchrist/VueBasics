<script lang="ts">
export default {
  setup() {
    const name = 'John Doe'
    const status = 'active'
    const tasks = ['Task One', 'Task Two', 'Task Three']
  },
}
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" v-bind:key="task">
      {{ task }}
    </li>
  </ul>

  <br />

  <button v-on:click="toggleStatus">Change Status</button>
</template>

<style scoped></style>
