<template>
    <!-- v-model -->
    <div>
        <h1>Formulario</h1>
        <input type="text" v-model="datos.nombre" placeholder="Nombre">
        <input type="text" v-model="datos.edad" placeholder="Edad">
        <p>{{ datos.nombre }} / {{ datos.edad }}</p>

        <div class="">
            <label for="terminos">
                <input v-model="datos.aceptar" type="checkbox" id="terminos"> Acepta los terminos y condiciones
            </label>
            <p>{{ datos.aceptar }}</p>
            <div v-if="datos.aceptar">
                <h3>Lenguajes de programacion</h3>
                    <p v-for="lenguaje in datos.lenguajes">
                        <label for="{{ lenguaje }}">
                            <input type="checkbox" id="{{ lenguaje }}">{{ lenguaje }}
                        </label>
                    </p>
            </div>
        </div>
        <p>{{ datos }}</p>
    </div>
</template>

<script setup lang="ts">
    import { ref, reactive } from 'vue';
    // reactive se recomienda para formularios o para un objeto qon muchas variables
    const datos = reactive({
        nombre: '',
        edad: 0,
        aceptar: false,
        lenguajes: ['Javascript', 'Typescript', 'Python', 'Java', 'C#', 'PHP']
    })
</script>

<style scoped>
    *{
        margin: 1rem;
    }
</style>