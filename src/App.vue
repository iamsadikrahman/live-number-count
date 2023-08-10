<script setup>
import { ref, onMounted } from "vue";

const projectNumbers = ref(0);
const workingHoursSpent = ref(0);
const happyClients = ref(0);

const startCounter = (valueRef, maxValue) => {
  const interval = setInterval(() => {
    valueRef.value++;
    if (valueRef.value === maxValue) {
      clearInterval(interval);
    }
  }, 1);
};

onMounted(() => {
  startCounter(projectNumbers, 400);
  startCounter(workingHoursSpent, 700);
  startCounter(happyClients, 300);
});
</script>

<template>
  <section
    class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 p-4 bg-slate-200 h-screen items-center p-5"
  >
    <div
      class="flex flex-col justify-center items-center bg bg-white border-b-4 border-yellow-500 rounded py-8"
    >
      <h2 class="text-8xl font-semibold">{{ projectNumbers }}+</h2>
      <p class="text-2xl">Succeeded Projects</p>
    </div>
    <div
      class="flex flex-col justify-center items-center bg-white border-b-4 border-green-500 rounded py-8"
    >
      <h2 class="text-8xl font-semibold">{{ workingHoursSpent }}+</h2>
      <p class="text-2xl">Working Hours Spent</p>
    </div>
    <div
      class="flex flex-col justify-center items-center bg-white border-b-4 border-purple-500 rounded py-8"
    >
      <h2 class="text-8xl font-semibold">{{ happyClients }}+</h2>
      <p class="text-2xl">Happy Clients</p>
    </div>
  </section>
</template>

<style scoped></style>
