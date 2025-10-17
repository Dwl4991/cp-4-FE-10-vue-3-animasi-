<script setup>
import { ref } from "vue";

const showText = ref(false);
</script>

<template>
  <main>
    <div class="container">
      <transition name="fade" mode="out-in">
        <h1 v-if="showText">He;llo world</h1>
        <h1 v-else="showText">Bye bye</h1>
      </transition>
      <button @click="showText = !showText">pijit</button>
    </div>
  </main>
</template>

<style scoped>
.cotainer {
  position: relative;
}
h1 {
  position: absolute;
}
button {
  margin-top: 50px;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}

.fade-enter-active {
  transition: all 1s ease;
}

.fade-leave-from {
  opacity: 1;
}
.fade-leave-to {
  opacity: 0;
}
.fade-leave-active {
  transition: all 1s ease;
}
</style>
