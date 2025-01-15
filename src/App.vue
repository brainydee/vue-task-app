<template>
  <the-header></the-header>
  <section class="container">
    <add-task @add-task="submitTask"></add-task>
    <task-list></task-list>
  </section>
</template>

<script>
import AddTask from "./components/AddTask.vue";
import TaskList from "./components/TaskList.vue";
import TheHeader from "./components/TheHeader";

export default {
  components: {
    TheHeader,
    AddTask,
    TaskList,
  },
  provide() {
    return {
      tasks: this.tasks,
      markCompleted: this.markCompleted,
      deleteTask: this.deleteTask,
    };
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          text: "Complete Vue.js tutorial",
          completed: false,
        },
        {
          id: 2,
          text: "Write a blog post about Vue components",
          completed: true,
        },
        {
          id: 3,
          text: "Fix bug in task management app",
          completed: false,
        },
        {
          id: 4,
          text: "Prepare for Vue.js interview",
          completed: false,
        },
        {
          id: 5,
          text: "Design task item component",
          completed: true,
        },
      ],
    };
  },
  methods: {
    markCompleted(id) {
      const task = this.tasks.find((task) => task.id === id);
      if (task) {
        task.completed = !task.completed;
      }
    },
    submitTask(task) {
      this.tasks.push({ id: Math.random(), text: task, completed: false });
    },
    deleteTask(id) {
      const taskIndex = this.tasks.findIndex((task) => task.id === id);
      this.tasks.splice(taskIndex, 1);
    },
  },
};
</script>

<style>
body {
  font-family: "Arial", sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f9;
  color: #333;
}

.container {
  max-width: 600px;
  margin: 2rem auto;
  padding: 1rem;
  background: #ffffff;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  font-size: 1.8rem;
  margin-bottom: 1rem;
  color: #555;
}
</style>
