<script setup>
  import { reactive, computed } from 'vue';

  const numbers = reactive({ true: 0, false: 0 });

  function calculate(boolean, operation) {
    if (numbers[boolean] - 1 >= 0 || operation) {
      return numbers[boolean] = numbers[boolean] += (operation) ? 1 : -1;
    }
  }
  function reset() {
    if (sum != 0) {
      numbers.true = 0;
      numbers.false = 0;
    }
  }
  const sum = computed(() => numbers.true + numbers.false);
</script>

<template>
  <h1>Calculator</h1>
  <div v-for="boolean of [true, false]">
    <p>Valor: {{ numbers[boolean] }}</p>
    <button @click="calculate(boolean, true)">+</button>
    <button @click="calculate(boolean, false)">-</button>
  </div>
  <button @click="reset()">reset</button>
  <p>Soma: {{ sum }}</p>
</template>

<style scoped> 

</style>
