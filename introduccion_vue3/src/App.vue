<!-- JS -->
<!-- Incluyendo el SETUP en script -->
<script setup lang="ts">
	import { ref,computed } from 'vue';

	const ahorros = ref(500);
	const depositar = ()=>{
		ahorros.value += 100;
	}

	const asignarClase = computed(()=>{
		if (ahorros.value > 500){
			return 'verde'
		}
		return 'rojo'
	})

</script>

<!-- HTML -->
<template>
	<h1 :class="asignarClase">Ahorros: ${{ ahorros }}</h1>
	<button @click="depositar()">Depositar</button>
</template>

<!-- CSS -->
<style scoped>
	.verde{
		color: green;
	}
	.rojo{
		color: rgb(255, 43, 43);
	}
</style>
