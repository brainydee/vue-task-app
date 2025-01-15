<template>
  <button><i class="fas fa-check"></i>&nbsp;<slot></slot></button>
</template>

<style scoped>
button {
  background-color: #007bff;
  color: #ffffff;
  border: none;
  border-radius: 4px;
  padding: 0.1rem 0.7rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
  height: 35px;
  margin-left: 7px;
}

button:hover {
  background-color: #0056b3;
}

button:disabled {
  background-color: #cccccc;
  cursor: not-allowed;
}
</style>
