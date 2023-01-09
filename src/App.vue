<template>
  <Questions />
  <CounterView />
</template>

<script setup>
import CounterView from "./components/CounterView.vue";
import Questions from "./components/Questions.vue";
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: #d6eadf;
  margin: 0;
  height: 100vh;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
body {
  margin: 0;
}
</style>
