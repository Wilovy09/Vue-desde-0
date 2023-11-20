<script setup lang="ts">
	const letras = ['a', 'b', 'c']
	const users = {
		name: 'Wilovy',
		edad: 21,
		confianza: true
	}
</script>

<template>
	<!-- v-for -->
	<!-- array | object | number | string | iterable -->
	<ul>
		<li v-for="(item, indice) in letras" :key="indice">
			{{ item }}
		</li>
	</ul>
	
	<!-- number -->
	<p>Listado de numeros</p>
	<span v-for="numero in 10" :key="numero">
		{{ numero }} /
	</span>

	<!-- string -->
	<p>Deletrear: </p>
	<ul>
		<li v-for="letra in 'Wilovy'">{{ letra }}</li>
	</ul>

	<!-- objeto -->
	<h1 v-for="(valor, propiedad, indice) in users" :key="indice">
		{{ indice }} / {{ propiedad }} / {{ valor}}
	</h1>

</template>

<style scoped>
	
</style>