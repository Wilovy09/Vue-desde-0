<template>
    <div class="card">
        <div class="card-body">
            <h1 class="card-title">
                {{ titulo }}
            </h1>
            <p class="card-text">
                {{ cuerpo }}
            </p>
        </div>
        <div class="card-footer">
            <Boton type="button" nombre="Borrar" @click="emit('borrar', id)"/>
        </div>
    </div>
</template>

<script setup lang="ts">
    import Boton from './Boton.vue';
    
    const emit = defineEmits(['borrar'])


    defineProps({
        titulo: {
            type: String,
            required: true,
            default: 'Titulo'
        },
        cuerpo: {
            type: String,
            required: true,
            default: 'Cuerpo'
        },
        id: {
            type: Number,
            required: true,
            default: 0
        }
    })
</script>

<style scoped>
.card{
    margin: 1rem;
}
</style>