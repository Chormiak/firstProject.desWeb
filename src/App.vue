<script setup>
  import { reactive, computed } from 'vue';

  const numbers = reactive({ true: 0, false: 0 });

  function calculate(boolean, local) {
    return numbers[boolean] += (local) ? 1 : -1;
  }
  const sum = computed(() => numbers.true + numbers.false);
</script>

<template>
  <h1>Calculator</h1>
  
  <div v-for="boolean of [true, false]">
    <p>Valor: {{ numbers[boolean] }}</p>
    <button @click="calculate(boolean, true)">Incrementar</button>
    <button @click="calculate(boolean, false)">Decrementar</button>
  </div>
  <p>Soma: {{ sum }}</p>
</template>

<style scoped> 

</style>
