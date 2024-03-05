<script setup>

import { ref } from 'vue';

const username = ref('');
const password = ref('');
const email = ref('');
</script>

<template>
    <form @submit.prevent="$emit('userInfo', username, email, password)">
        <input type="text" v-model="username">
        <input type="text" v-model="email">
        <input type="text" v-model="password">
        <button type="submit">Submit</button>
    </form>
</template>