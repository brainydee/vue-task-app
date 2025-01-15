<template>
  <section class="box">
    <div class="add-task">
      <input
        type="text"
        placeholder="Enter a new task..."
        v-model="newTask"
        @keyup.enter="addTask"
      />
    </div>
    <base-button @click="addTask">Add Task</base-button>
  </section>
</template>

<script>
import BaseButton from "./UI/BaseButton.vue";
export default {
  components: { BaseButton },
  emits: ["add-task"],
  data() {
    return {
      newTask: "",
    };
  },
  methods: {
    addTask() {
      this.$emit("add-task", this.newTask);
    },
  },
};
</script>

<style scoped>
.box {
  display: flex;
  flex-direction: row;
}

.add-task {
  display: flex;
  flex: 1;
  gap: 1rem;
  margin-bottom: 1rem;
}

.add-task input {
  flex: 1;
  padding: 0.5rem;
  font-size: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  outline: none;
  transition: border-color 0.3s ease;
}

.add-task input:focus {
  border-color: #007bff;
}
</style>
