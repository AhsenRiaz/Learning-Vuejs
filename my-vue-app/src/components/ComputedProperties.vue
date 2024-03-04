<script setup>
import { ref, computed } from 'vue';

let counter = ref(0);

const incrementCounter = () => {
    counter.value++;
}

const squaredCounter = computed(() =>  counter.value ** 2);


</script>

<template>
    <h2>Counter:{{ counter }} </h2>
    <p>Squared Counter : {{ squaredCounter }}</p>
    <button @click="incrementCounter">Increment Counter</button>

</template>

<style></style>