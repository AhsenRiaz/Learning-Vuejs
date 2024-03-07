<script setup>
import { ref, watch, reactive } from 'vue';

const username = ref("Alice")
const obj = reactive({username:"Julie"})

watch(username, (newValue, oldValue) => {
    console.log("old value", oldValue)
    console.log("newValue", newValue)
});

watch(() => obj.username, (newValue, oldValue) => {
    console.log("old value", oldValue)
    console.log("newValue", newValue)
})

// we can also keep track of multiple states simultaneously this way

watch([username, () => obj.username], (newValue, oldValue) => {
    console.log("old value >>>", oldValue)
    console.log("newValue >>>>", newValue)
})


</script>

<template>
    <div>
        <h1>Ref: {{ username }}</h1>
        <h1>Reactive: {{ obj.username }}</h1>

        <button @click="username = 'Bob'">Click Here to update ref</button>
        <button @click="obj.username = 'John'">Click Here to update reactive</button>
            
    </div>
</template>