<template>
  <div class="counters">
    <Counter v-for="team in teams" :key="team" :name="team" />
  </div>
</template>

<script setup>
import Counter from "./Counter.vue";

const teams = ["Discombobulated", "Kottaliza"];
</script>

<style>
.counters {
  display: flex;
  justify-content: space-around;
}
</style>
