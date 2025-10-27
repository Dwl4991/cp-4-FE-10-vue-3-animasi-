<script setup>
import { ref } from "vue";

const tasks = ref(["Learn Vue 3", "Learn CSS", "Learn JavaScript"]);
const newTask = ref("");

function addTask() {
  if (newTask.value) {
    tasks.value.unshift(newTask.value);
    newTask.value = "";
  }
}

function removeTask(task) {
  tasks.value = tasks.value.filter((t) => t !== task);
}
</script>

<template>
  <main>
    <div class="container">
      <input type="text" autofocus v-model="newTask" @keyup.enter="addTask()" />
      <div class="card-list" v-for="task in tasks" :key="task" @click="removeTask(task)">{{ task }}</div>
    </div>
  </main>
</template>

<style scoped>
.container {
  max-width: 300px;
  margin: 0 auto;
}
.container input {
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
  margin-bottom: 20px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
}

.card-list {
  width: 300px;
  background-color: #f9f9f9;
  padding: 5px 10px;
  margin-top: 10px;
  border-radius: 5px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  cursor: pointer;
}
</style>
