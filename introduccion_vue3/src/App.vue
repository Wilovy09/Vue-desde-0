<script setup lang="ts">
	const puntajeCrediticio = 700
</script>

<template>
	<!-- v-show -->
	<!-- aplica un display none si no se cumple la condicion -->
	<p v-show="puntajeCrediticio >= 700">Test</p>
	

</template>

<style scoped>
	
</style>