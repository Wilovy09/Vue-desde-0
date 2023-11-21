<!-- JS -->
<script setup lang="ts">
	import { ref } from "vue";

	const status = ref<boolean>(false)

	const ahorros = ref<number>(500);

	const depositar = ()=>{
		status.value = !status.value;
		
		ahorros.value += 100;
		console.log(ahorros);
	}
</script>

<!-- HTML -->
<template>
	<!-- Reactividad -->
	<h1>${{ ahorros }}</h1>
	<button @click="depositar()">Depositar $100</button>
	{{ status }}
	<button @click="status = !status ">Cambiar status</button>
</template>

<!-- CSS -->
<style scoped>
	
</style>
