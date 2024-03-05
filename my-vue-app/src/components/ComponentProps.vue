<script setup>
import { computed } from 'vue';

// const props = defineProps(['name', 'buttonColor'])

// another way of defining props

const props = defineProps({
    name: String,
    buttonColor: String,
    fullName: {
        type: String,
        required: true,
        default: "Anon"
    },
    employee: {
        type: String,
        required: false,
        validator: (propValue) => {
            return ['Alice', 'Bob'].includes(propValue)
        }
    },
    age: {
        type: Number,
        validator: (propValue) => {
            return propValue > 20
        }
    }
})


</script>

<template>
    <div>
        <h4>{{ name }}</h4>
        <h1>{{ props.buttonColor }}</h1>
        <h1>{{ props.fullName }}</h1>
        <button v-show="props.buttonColor" :style="{ backgroundColor: props.buttonColor }">Dynamic Button</button>
    </div>
</template>
