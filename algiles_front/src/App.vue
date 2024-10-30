<script setup>
import { ref } from 'vue';
import Juego from './components/Juego.vue';
import ContenedorPalabra from './components/ContenedorPalabra.vue';
import Keyboard from './components/Keyboard.vue'


const palabra = ref('SCRUM'); 
const letrasCorrectas = ref([]);
const vidasRestantes = ref(6); // Máximo de vidas = 6
const letrasUsadas = ref([]);


function handleGuess(letra) {

}
</script>




<template>
  <div>
    <h1>Juego de Ahorcado</h1>
    <Juego :palabra="palabra" :vidasRestantes="vidasRestantes" :letras-correctas="letrasCorrectas" />
    <ContenedorPalabra :palabra="palabra" :letrasCorrectas="letrasCorrectas" />
    <Keyboard @letterGuess="handleGuess" :letrasUsadas="letrasUsadas" />
  </div>
</template>
