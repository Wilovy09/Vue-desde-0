<script setup lang="ts">
	const puntajeCrediticio = 800
</script>

<template>
	<!-- v-if & v-else-if & v-else tienen que estar juntas una encima de otra -->
	<p v-if="puntajeCrediticio >= 900">Excelente cliente</p>
	<p v-else-if="puntajeCrediticio >= 600">Cliente regular</p>
	<p v-else>Cliente pesimo</p>

</template>

<style scoped>
	
</style>