<script setup>
import { ref, TransitionGroup } from "vue";

const tasks = ref(["Learn Vue 3", "Learn CSS", "Learn JavaScript"]);
const newTask = ref("");

function addTask() {
  if (newTask.value) {
    tasks.value.unshift(newTask.value);
    newTask.value = "";
  }
}

function removeTask(index) {
  tasks.value.splice(index, 1);
}
</script>

<template>
  <main>
    <div class="container">
      <input type="text" autofocus v-model="newTask" @keyup.enter="addTask()" />
      <TransitionGroup name="list">
        <div class="card-list" v-for="task in tasks" :key="task" @click="removeTask(tasks.indexOf(task))">{{ task }}</div>
      </TransitionGroup>
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
  margin-top: 20px;
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

.list-enter-from {
  opacity: 0;
  transform: scale(0.6);
}
.list-enter-to {
  opacity: 1;
  transform: scale(1);
}
.list-enter-active {
  transition: all 0.5s ease;
}

.list-leave-from {
  opacity: 1;
  transform: scale(1);
}
.list-leave-to {
  opacity: 0;
  transform: scale(0);
}
.list-leave-active {
  transition: all 0.5s ease;
  position: absolute;
}

.list-move {
  transition: all 0.5s ease;
}
</style>
