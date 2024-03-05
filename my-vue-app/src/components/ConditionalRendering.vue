<script setup>
const isTrue = true;
const isFalse = false;
</script>

<template>
    <div>
        <p v-if="isTrue">Only show if true</p>
    </div>
</template>

<style></style>