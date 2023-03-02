<template>
  <input type="number" v-model="num" />
  <button @click="addNumber">Add</button>
  <div>{{ records  }}</div>
 
  <ul v-for="row in records">
    <li>{{ row * 5 }}</li>
  </ul>

  <h1><strong>{{ total }}</strong></h1>

</template>

<script setup lang="ts">
import { ref, reactive } from "vue";

const num = ref<number>(0);
const total = ref<number>(0);

const records = reactive<number[]>([]);

function addNumber() {
  records.push(num.value);
  Sum();
}

function Sum() {
  total.value = total.value + num.value;
  return total;
}

</script>
