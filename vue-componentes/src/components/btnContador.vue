<template>
    <button @click="contador++">Contador: {{ contador }}</button>
</template>

<script setup lang="ts">
import { ref } from "vue";

const contador = ref(0);

</script>

<style scoped>

</style>