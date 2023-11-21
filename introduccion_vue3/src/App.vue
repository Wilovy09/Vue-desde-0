<!-- JS -->
<!-- <script lang="ts">
	import { defineComponent, ref } from 'vue';

	export default defineComponent({
		components:{},
		setup(){
			const ahorros = ref(500)

			return {ahorros}
		},
		methods:{
			depositar(){
				this.ahorros += 100;
			}
		},
		computed:{}
	});
</script> -->

<!-- Incluyendo el SETUP en script -->
<script setup lang="ts">
	import { ref } from 'vue';

	const ahorros = ref(500);
	const depositar = ()=>{
		ahorros.value += 100;
	}

</script>

<!-- HTML -->
<template>
	<h1>Ahorros: ${{ ahorros }}</h1>
	<button @click="depositar()">Depositar</button>
</template>

<!-- CSS -->
<style scoped>
	
</style>
