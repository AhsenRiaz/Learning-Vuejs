<script setup>
import { reactive, ref } from 'vue';

let countRef = ref(0);



let initialState = reactive({
    count: 3,
    users: ['alice', 'bob']
})

const appendUser = () => {
    initialState.users.push("ahsen")
}

</script>

<template>
    <h2>Current countRef:{{ countRef }} </h2>

    <h2>Current Reactive Count: {{ initialState.count }}</h2>

    <h2 >{{ initialState.users }}</h2>

    <button @:click="countRef++">Increase count ref</button>
    <button @:click="initialState.count--">Increase count ref</button>
    <button @:click="appendUser">Append user</button>


</template>

<style></style>