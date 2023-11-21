<!-- EJERCICIO #1 -->
<!-- 
	- Mostrar nuestro ahorro
	- Btn para depsitar
	- Btn para retirar
	- Listado de movimientos de un array
	- Diferenciar si es un deposito o un retiro
	- El boton retirar se debe bloquear si no tenemos dinero

	Conocimientos
	v-bind / v-if / v-else-if / v-else / v-for / v-on / ref / computed
 -->

<!-- JS -->
<script setup lang="ts">
	import {computed, ref} from "vue";
	// interfaz
	interface iMovimiento{
		monto: number;
		saldoActual: number;
	}
	// const
	const ahorros = ref(0);
	const movimientos = ref<iMovimiento[]>([]);
	// deposito
	const depositar = (cantidad:number)=>{
		ahorros.value += cantidad;
		
		movimientos.value.push({
			monto: cantidad,
			saldoActual: ahorros.value
		})
	}
	const realizarDeposito = () => {
		depositar(100); // Realiza un depósito de $100
	};
	// Retiro
	const retirar = (cantidad:number)=>{
		ahorros.value -= cantidad;
		
		movimientos.value.push({
			monto: -cantidad,
			saldoActual: ahorros.value
		})
	}
	const realizarRetiro = () => {
		retirar(100); // Realiza un retiro de $100
	};
	// deshabilitar btn
	const deshabilitarBTN = computed(()=>{
		if (ahorros.value == 0){
			return true
		}
		return false
	})

	// invertir
	const invertirARRAY = computed(()=>{
		return movimientos.value.reverse();
	})

	
</script>

<!-- HTML -->
<template>
	<h1>Ahorros <br> ${{ ahorros }}</h1>

	<button @click="realizarDeposito">Depositar $100</button>
	<br>
	<br>
	<button @click="realizarRetiro" :disabled="deshabilitarBTN" >Retirar $100</button>
	<br>
	<br>
	<div class="">
		<h4>Movimientos</h4>
		<ul>
			<li v-for="(movimiento, index) in invertirARRAY" :key="index">
				<span v-if="movimiento.monto > 0">
					Deposito| 
				</span>
				<span v-else>
					Retiro  |
				</span>
				Movimiento: {{ movimiento.monto }} |Saldo: {{ movimiento.saldoActual }}
			</li>
		</ul>
	</div>
</template>

<!-- CSS -->
<style scoped>
	
</style>
