<template>
  <li class="task-item">
    <span :class="{ completed: task.completed }">
      {{ task.text }}
    </span>
    <div class="actions">
      <i
        class="fas fa-check-circle complete-icon"
        title="Mark as complete"
        v-on:click="markCompleted(task.id)"
      >
      </i>
      <i
        class="fas fa-trash delete-icon"
        @click="deleteTask(task.id)"
        title="Delete task"
      >
      </i>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      required: true,
    },
  },
  inject: ["markCompleted", "deleteTask"],
};
</script>

<style scoped>
.task-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  margin-bottom: 0.5rem;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease;
}

.task-item:hover {
  background-color: #f1f1f1;
}

.task-item span {
  flex: 1;
  font-size: 1rem;
  cursor: pointer;
}

.task-item span.completed {
  text-decoration: line-through;
  color: #888;
}

.actions {
  display: flex;
  gap: 0.5rem;
}

.actions i {
  cursor: pointer;
  font-size: 1.2rem;
  transition: color 0.3s ease;
}

.actions .complete-icon {
  color: #28a745;
}

.actions .complete-icon:hover {
  color: #218838;
}

.actions .delete-icon {
  color: #dc3545;
}

.actions .delete-icon:hover {
  color: #c82333;
}
</style>
