<script setup>
import { ref } from "vue";
</script>

<template>
  <main>
    <div class="container">
      <input type="text" autofocus />
      <div>Task 1</div>
      <div>Task 2</div>
      <div>Task 3</div>
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
</style>
