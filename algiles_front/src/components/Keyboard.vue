<script setup>
import { ref, defineProps, defineEmits } from 'vue';

// Definición de propiedades y emisión de eventos
const props = defineProps({
    letrasUsadas: Array
});

const emit = defineEmits(['letterGuess']);

// Estado reactivo
const letras = ref('ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split(''));

// Función para manejar el evento de adivinanza
function guessLetter(letter) {
    emit('letterGuess', letter);
}
</script>

<template>
    <div>
        <button v-for="letra in letras" :key="letra" @click="guessLetter(letra)"
            :disabled="letrasUsadas.includes(letra)">
            {{ letter }}
        </button>
    </div>
</template>
