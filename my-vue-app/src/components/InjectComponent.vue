<script setup>
import {inject} from 'vue'

const data = inject("data");
</script>

<template>
    <div>
        <h4>Games</h4>
        <h6>{{ data.name }}</h6>
        <ul v-for="(genre, index) in data.genre" :key="index">
            <li>{{ genre }}</li>
        </ul>
        <ol v-for="({name, course}, index) in data.students" :key="index"  >
            <li  >
                student:{{ name }}
            </li>
            <li>course: {{ course }}</li>
        </ol>
    </div>
</template>