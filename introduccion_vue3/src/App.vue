<!-- JS -->
<script setup lang="ts">

</script>
<!-- HTML -->
<template>
	<!-- por defecto -->
	<button onclick="alert('Ok')">Enviar</button>
	<!-- v-on o @ -->
	<button @click.right.prevent="console.log('Ok')">Enviar</button>

	<input @blur="console.log('Ok')" type="text">
</template>
<!-- CSS -->
<style scoped>
	
</style>
