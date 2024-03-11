<script setup>
import { reactive, computed, provide } from "vue";
import Header from './components/Header.vue'
import FormCalc from './components/FormCalc.vue'
import Result from './components/Result.vue'

const state = reactive({
    num1: '',
    num2: '',
    operacao: 'soma',
});

const result = computed(() => {
    if (state.num1 === '' || state.num2 === '') {
        return '';
    }

    const num1 = parseFloat(state.num1);
    const num2 = parseFloat(state.num2);
    const operacao = state.operacao;

    switch (operacao) {
        case 'soma':
            return (num1 + num2).toFixed(2);
        case 'subtracao':
            return (num1 - num2).toFixed(2);
        case 'multiplicacao':
            return (num1 * num2).toFixed(2);
        case 'divisao':
            return num2 !== 0 ? (num1 / num2).toFixed(2) : 'Erro: divisão por zero';
        default:
            return 'Operação inválida';
    }
});


provide('state', state);
provide('result', result);
</script>

<template>
    <div class="container">
        <Header />
        <FormCalc />
        <Result />
    </div>
</template>