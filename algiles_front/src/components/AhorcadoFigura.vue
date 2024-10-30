<script setup>
import { defineProps } from 'vue';

// Definición de propiedades
const props = defineProps({
    vidasRestantes: Number
});
</script>

<template>
    <div>
        <p>Vidas Restantes: {{ vidasRestantes }}</p>
        <div class="hangman">
            <!-- Cada una de estas partes se muestra solo cuando vidasRestantes es mayor o igual al valor correspondiente -->
            <div v-if="vidasRestantes >= 1" class="hangman__base"></div>
            <div v-if="vidasRestantes >= 2" class="hangman__pole"></div>
            <div v-if="vidasRestantes >= 3" class="hangman__beam"></div>
            <div v-if="vidasRestantes >= 4" class="hangman__rope"></div>
            <div v-if="vidasRestantes >= 5" class="hangman__head"></div>
            <div v-if="vidasRestantes >= 6" class="hangman__body"></div>
            <div v-if="vidasRestantes >= 7" class="hangman__left-arm"></div>
            <div v-if="vidasRestantes >= 8" class="hangman__right-arm"></div>
            <div v-if="vidasRestantes >= 9" class="hangman__left-leg"></div>
            <div v-if="vidasRestantes >= 10" class="hangman__right-leg"></div>
        </div>
    </div>
</template>


<style scoped>
.hangman {
    position: relative;
    width: 100px;
    height: 200px;
    margin-top: 20px;
}

/* Estilos para las diferentes partes del ahorcado */
.hangman__base {
    width: 100px;
    height: 10px;
    background: black;
    position: absolute;
    bottom: 0;
}

.hangman__pole {
    width: 10px;
    height: 150px;
    background: black;
    position: absolute;
    left: 0;
    bottom: 10px;
}

.hangman__beam {
    width: 60px;
    height: 10px;
    background: black;
    position: absolute;
    left: 0;
    top: 0;
}

.hangman__rope {
    width: 2px;
    height: 20px;
    background: black;
    position: absolute;
    left: 55px;
    top: 10px;
}

.hangman__head {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 2px solid black;
    position: absolute;
    left: 45px;
    top: 30px;
}

.hangman__body {
    width: 2px;
    height: 50px;
    background: black;
    position: absolute;
    left: 54px;
    top: 50px;
}

.hangman__left-arm {
    width: 20px;
    height: 2px;
    background: black;
    position: absolute;
    left: 34px;
    top: 60px;
    transform: rotate(-45deg);
}

.hangman__right-arm {
    width: 20px;
    height: 2px;
    background: black;
}

</style>