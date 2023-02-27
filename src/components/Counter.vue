<template>
  <div class="counter">
    <h2>{{ props.name }}</h2>
    <h1>{{ count }}</h1>
    <div class="score-box">
      <div class="button" @click="count--">-</div>
      <div class="button" @click="count++">+</div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  name: String,
});

const count = ref(0);
</script>

<style scoped>
.counter {
  display: block;
  padding: 1em;
}
h2 {
  margin-bottom: 0;
}
h1 {
  font-weight: bold;
  font-size: 6rem;
  margin: 0;
}
.button {
  cursor: pointer;
  background-color: #b8e0d2;
  padding: 0.5em 1.5em;
  border-radius: 1em;
  margin: 0 0.5em;
  width: 30px;
}
.button:hover {
  background-color: #83c9b0;
}

.score-box {
  display: flex;
}
</style>
