<template>
  <div class="task-list">
    <h2>Your Tasks</h2>
    <div v-if="tasks.length > 0">
      <task-item v-for="task in tasks" :task="task" :key="task.id"></task-item>
    </div>
    <p v-else>No task to display. Add New Task.</p>
  </div>
</template>

<script>
import TaskItem from "./TaskItem.vue";

export default {
  components: {
    TaskItem,
  },
  inject: ["tasks"],
};
</script>

<style scoped>
.task-list {
  margin: 1rem 0;
  padding: 1rem;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.task-list h2 {
  margin-bottom: 1.5rem;
  font-size: 1rem;
  color: #333;
  font-weight: bold;
}

.task-list ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>
