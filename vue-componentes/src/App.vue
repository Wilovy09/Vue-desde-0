<template>
	<!-- <Boton type="" nombre="btn"/>
	<Boton type="reset" nombre="disable" disabled />
	<Formulario /> -->
	<CardNoticiasVue v-for="noticia in noticias" 
					 :id="noticia.id" 
					 :key="noticia.id" 
					 v-bind:titulo="noticia.titulo" 
					 :cuerpo="noticia.cuerpo"
					 @borrar="eliminiarNoticia"/>
</template>

<script setup lang="ts">
	import { ref } from 'vue';
	import Boton from './components/Boton.vue';
	import Formulario from './components/Formulario.vue';
	import CardNoticiasVue from './components/CardNoticias.vue';

	const noticias = ref([
    {
        id: 1,
        titulo: "Nueva investigación revela posibles indicios de vida en Marte",
        cuerpo: "Un equipo de científicos ha encontrado compuestos orgánicos en muestras recogidas por rovers en la superficie marciana..."
    },
    {
        id: 2,
        titulo: "Aumentan las tensiones en la cumbre de líderes mundiales",
        cuerpo: "Los líderes de diferentes naciones no logran llegar a acuerdos clave sobre temas de comercio y seguridad..."
    },
    {
        id: 3,
        titulo: "Startup de inteligencia artificial consigue financiamiento récord",
        cuerpo: "Una startup enfocada en el desarrollo de inteligencia artificial ha recaudado una cifra sin precedentes en su última ronda de financiamiento..."
    },
    {
        id: 4,
        titulo: "Descubren nueva especie marina en las profundidades del océano",
        cuerpo: "Investigadores han encontrado una especie nunca antes vista en las aguas más profundas de los océanos, planteando preguntas sobre la biodiversidad en esos entornos..."
    },
    {
        id: 5,
        titulo: "Avance médico prometedor en la lucha contra enfermedades neurodegenerativas",
        cuerpo: "Un equipo de científicos afirma haber desarrollado una terapia experimental que muestra resultados alentadores en la reversión de síntomas de enfermedades como el Alzheimer y el Parkinson..."
    }
	]);

	const eliminiarNoticia = (id:number) => {
        noticias.value = noticias.value.filter(x => x.id !== id);
    }

</script>

<style scoped></style>
