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
    <div class="keyboard">
        <button v-for="letra in letras" :key="letra" @click="guessLetter(letra)"
            :disabled="letrasUsadas.includes(letra)" class="keyboard__button">
            {{ letra }}
        </button>
    </div>
</template>

<style scoped>
.keyboard {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 10px;
    max-width: 400px;
    margin: 20px auto;
}

.keyboard__button {
    padding: 10px;
    font-size: 1.2em;
    border: 1px solid #333;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s, color 0.3s;
}

.keyboard__button:disabled {
    background-color: #ddd;
    color: #aaa;
    cursor: not-allowed;
}

.keyboard__button:not(:disabled):hover {
    background-color: #007BFF;
    color: #fff;
    border-color: #007BFF;
}
</style>