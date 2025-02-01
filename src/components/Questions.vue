<template>
  <div class="wrapper">
    <div class="buttons">
      <div class="button" :class="{ active: selectedQuestion == -1 }" @click="selectedQuestion = -1">
        <img :src="imageUrl" alt="Example Image" class="homeIcon">
      </div>
    </div>
    <div class="question">
      <template v-if="selectedQuestion >= 0">
        <h2>{{ questions.at(selectedQuestion).t }}</h2>
        <p v-for="q in questions.at(selectedQuestion).q" :key="q">
          {{ q }}
        </p>
      </template>
      <template v-else>
        <h1>Den gemensamma nämnaren</h1>
        <h2><em> - Dagfalk Family Edition</em></h2>
        <p>Dags för lek! Vänta med att klicka på någon av knapparna tills spelledarna säger till.</p>
      </template>
    </div>
    <div class="buttons">
      <div v-for="(question, index) in questions" :key="question" class="button"
        :class="{ active: selectedQuestion == index }" @click="selectedQuestion = index">
        {{ index + 1 }}
      </div>
    </div>
  </div>
</template>

<script setup>
import imageUrl from '@/assets/home.png'; // Vue 3 (Vite/Webpack)
import { ref } from "vue";
import { johannaQuestions } from "../questions/johannaBirthday";

const selectedQuestion = ref(-1);
const questions = johannaQuestions;
</script>

<style scoped>
p {
  margin: 0.5em;
}

.wrapper {
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  height: 100%
}

.homeIcon {
  height: 1.25rem;
}

.question {
  display: flex;
  flex-direction: column;
  justify-content: center;
  flex-grow: 1;
}

.buttons {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.button {
  cursor: pointer;
  background-color: #b8e0d2;
  padding: 0.5em 1em;
  border-radius: 1em;
  font-size: 1.25em;
  font-weight: bold;
  width: 1.5rem;
  display: flex;
  justify-content: center;
  height: 1.75rem;
  align-items: center;
}

.button:hover {
  background-color: #83c9b0;
}

.active {
  background-color: #83c9b0;
}
</style>
