<script setup lang="ts">
	const saludo = "Hola a todos"
	const btnHTML = '<button>Enviar</button>'
	const color = 'color: red; background-color: black;'
	const web = 'https://google.com'
	const ahorros = 350;
</script>

<template>

	<h1>Introduccion a Vue</h1>
	<h2>{{ saludo }}</h2>
	<p>{{ btnHTML }}</p>
	<samp v-html="btnHTML" ></samp>
	<p v-bind:style="color">TEST</p>
	<a :href="web">Google</a>
	{{ 8*8 }}
	<h2 :style="`color:${ahorros >= 200 ? 'green ' : 'red'}`" >$ {{ ahorros }}</h2>
	<h2 :class="ahorros >= 200 ? 'confondos' : 'sinfondo'" >$ {{ ahorros }}</h2> <!-- Ni idea porque no funciona-->
	<h2>{{ saludo.toLocaleUpperCase() }}</h2>

</template>

<style scoped>
	.sinfondo{
		color: red;
	}
	.confondos{
		color: green;
	}
</style>