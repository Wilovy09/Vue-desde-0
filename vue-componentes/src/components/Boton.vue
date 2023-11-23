<template>
    <button :type="type"
            class="btn btn-primary" 
            :disabled="disable">
            {{ nombre }}
    </button>
</template>

<script setup lang="ts">

    type TIPO_BTN = 'button' | 'submit' | 'reset';
    
    const props = defineProps({
        nombre: {
            type: String,
            required: true,
            default: 'Boton'
        },
        disable:{
            type: Boolean,
            required: false,
            default: false
        },
        type: {
            type: String as ()=> TIPO_BTN,
            validator(value: string){
                return ['button', 'submit', 'reset'].includes(value)
            },
            required: true,
            default: 'button'
        }
    });
  

</script>

<style scoped></style>