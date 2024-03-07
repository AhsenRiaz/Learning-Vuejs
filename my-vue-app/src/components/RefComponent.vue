<script setup>
import { ref, onMounted } from 'vue';

const inputRef = ref('')

const anotherRef = (el) => {
    el.textContent = 'Text changed'
}

onMounted(() => {
    console.log(inputRef)
    inputRef.value.focus()
})

</script>

<template>
    <input type="text" ref="inputRef" >

    <p :ref="anotherRef" >This is text</p>
</template>