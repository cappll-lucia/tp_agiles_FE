<script setup>
    import { defineProps } from 'vue';

    const props = defineProps({
        palabra: String,
        letrasCorrectas: Array
    });
</script>

<template>
    <div>
        <span v-for="letra in palabra" :key="letra">
            {{ letrasCorrectas.includes(letra) ? letra : '_' }}
        </span>
    </div>
</template>

