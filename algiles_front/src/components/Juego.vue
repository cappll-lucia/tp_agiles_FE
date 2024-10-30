<script setup>
    import { ref, defineProps } from 'vue';
    import AhorcadoFigura from './AhorcadoFigura.vue';

    // Definición de propiedades
    const props = defineProps({
        vidasRestantes: Number,
        palabra: String,
        letrasCorrectas: Array
    });

    // Estado reactivo
const maxAttempts = ref(6);
</script>



<template>
    <div>
        <AhorcadoFigura :vidasRestantes="vidasRestantes" />
        <p v-if="vidasRestantes >= maxAttempts">¡Perdiste! La palabra era {{ palabra }}</p>
        <p v-else-if="palabra.split('').every(letra => letrasCorrectas.includes(letra))">¡Ganaste!</p>
    </div>
</template>