<script setup>
import { inject } from "vue";

const state = inject('state');
</script>

<template>
    <div class="col">
        <form class="form-inline d-flex align-items-center">
            <div class="form-group mx-2 flex-grow-1">
                <input type="number" class="form-control border border-dark" placeholder="Digite um número"
                    v-model="state.num1" />
            </div>
            <div class="form-group mx-2 flex-grow-0">
                <select name="operacao" class="form-control border border-dark" v-model="state.operacao">
                    <option value="soma">+</option>
                    <option value="subtracao">-</option>
                    <option value="multiplicacao">*</option>
                    <option value="divisao">/</option>
                </select>
            </div>
            <div class="form-group mx-2 flex-grow-1">
                <input type="number" class="form-control border border-dark" placeholder="Digite outro número"
                    v-model="state.num2" />
            </div>
        </form>
    </div>
</template>

<style scoped>
input[type=number]::-webkit-inner-spin-button,
input[type=number]::-webkit-outer-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
</style>