<script setup>
import { storeToRefs } from "pinia";
import { useCounterStore } from "@/stores/counter";

const store = useCounterStore();
const { count, doubleCount } = storeToRefs(store);
const { increment, decrement } = store;
</script>

<template>
  <main>
    <h1>{{ count }}</h1>
    <div>
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </div>
    <h2>doubled: {{ doubleCount }}</h2>
    <input type="number" v-model="count" />
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
button {
  width: 3rem;
  height: 3rem;
  font-weight: bold;
  font-size: 1.5rem;
  border-radius: 0.5em;
  margin-left: 0.5em;
  margin-right: 0.5em;
}
input {
  padding: 1em;
  margin-top: 1em;
  border-radius: 0.5em;
  font-size: 1rem;
}
</style>
