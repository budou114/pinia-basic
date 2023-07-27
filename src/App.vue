<script setup lang="ts">
import { computed } from "vue";
import { useCounterStore } from "../src/stores/counter";

const counterStore = useCounterStore();
const count = computed((): number => {
  return counterStore.counter;
});

const doubleCount = computed(() : number => {
  return counterStore.doubleCount;
});

const onIncrementClick = () => {
  counterStore.incrementCount();
};

</script>

<template>
  <p>現在のポイント:{{count}}</p>
  <p>現在のポイントさらに倍:{{doubleCount}}</p>
  <button @click="onIncrementClick">加算</button>
</template>
