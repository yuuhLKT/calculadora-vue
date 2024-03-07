<script setup>
import { inject } from 'vue';

const result = inject('result');
</script>

<template>
    <div class="col">
        <div class="alert alert-primary mt-4 text-center resultado" role="alert">
            Resultado: {{ result }}
        </div>
    </div>
</template>

<style scoped>
    .resultado {
        font-size: 1.2rem;
        font-weight: bold;
    }
</style>