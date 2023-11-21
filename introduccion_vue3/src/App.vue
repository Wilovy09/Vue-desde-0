<script setup lang="ts">
	const preguntas = [
  {
    pregunta: "¿Cuál es la capital de Australia?",
    opciones: ["Melbourne", "Sídney", "Canberra", "Brisbane"],
    respuestaCorrecta: 2 // El índice de la respuesta correcta (en este caso, Canberra)
  },
  {
    pregunta: "¿Quién escribió 'El principito'?",
    opciones: ["Antoine de Saint-Exupéry", "J.K. Rowling", "Charles Dickens", "F. Scott Fitzgerald"],
    respuestaCorrecta: 0 // El índice de la respuesta correcta (en este caso, Antoine de Saint-Exupéry)
  },
  {
    pregunta: "¿Cuántos continentes hay en el mundo?",
    opciones: ["4", "6", "7", "5"],
    respuestaCorrecta: 2 // El índice de la respuesta correcta (en este caso, 7)
  },
  {
    pregunta: "¿En qué año llegó el hombre a la Luna por primera vez?",
    opciones: ["1969", "1973", "1958", "1982"],
    respuestaCorrecta: 0 // El índice de la respuesta correcta (en este caso, 1969)
  },
  {
    pregunta: "¿Cuál es el país más grande del mundo por área?",
    opciones: ["Canadá", "Estados Unidos", "Rusia", "China"],
    respuestaCorrecta: 2 // El índice de la respuesta correcta (en este caso, Rusia)
  },
  {
    pregunta: "¿Quién fue el primer presidente de Estados Unidos?",
    opciones: ["Thomas Jefferson", "George Washington", "John Adams", "James Madison"],
    respuestaCorrecta: 1 // El índice de la respuesta correcta (en este caso, George Washington)
  },
  {
    pregunta: "¿Cuál es el metal más abundante en la corteza terrestre?",
    opciones: ["Hierro", "Aluminio", "Oro", "Plata"],
    respuestaCorrecta: 1 // El índice de la respuesta correcta (en este caso, Aluminio)
  },
  {
    pregunta: "¿Cuál es la montaña más alta del mundo?",
    opciones: ["Monte Everest", "K2", "Monte Kilimanjaro", "Matterhorn"],
    respuestaCorrecta: 0 // El índice de la respuesta correcta (en este caso, Monte Everest)
  },
  {
    pregunta: "¿En qué país se encuentra la Torre Eiffel?",
    opciones: ["Italia", "Francia", "Alemania", "España"],
    respuestaCorrecta: 1 // El índice de la respuesta correcta (en este caso, Francia)
  },
  {
    pregunta: "¿Cuál es el océano más grande?",
    opciones: ["Océano Atlántico", "Océano Pacífico", "Océano Índico", "Océano Ártico"],
    respuestaCorrecta: 1 // El índice de la respuesta correcta (en este caso, Océano Pacífico)
  }
];

</script>

<template>
	<!-- Bucles anidados -->
	<div>
		<h1>Cuestionario</h1>
		<hr>
		<div v-for="(pregunta, indice) in preguntas" :key="indice">
			<h2>{{ indice+1 }}. {{ pregunta.pregunta }}</h2>
			
			<div v-for="(opciones, indeiceOpciones) in pregunta.opciones" :key="indiceOpciones">
				<label for="checkbox">
					<!-- con v-if & v-else -->
					<span v-if="pregunta.respuestaCorrecta === indeiceOpciones">✅</span>
					<span v-else>❌</span>
					<input type="checkbox" name="checkbox">{{ opciones }}
					<!-- con terniaria -->
					{{ pregunta.respuestaCorrecta === indeiceOpciones ? '✅' : '❌' }}
				</label>
			</div>
			
		</div>

	</div>

</template>

<style scoped>
	
</style>