<template>
    <div class="calculator">
        <h1 class="calculator__title">calculator</h1>
        <div class="input-group">
            <div class="input-group__field">
                <input type="number" v-model.number="state.num1" @input="calculate"
                    placeholder="Digite o Primeiro numero" />
                <input type="number" v-model.number="state.num2" @input="calculate"
                    placeholder="Digite o Segundo numeri">
            </div>
            <div class="input-group__field input-group__field--select">
                <select v-model="state.operation" @change="calculate">
                    <option value="add">+</option>
                    <option value="subtract">-</option>
                    <option value="multiply">*</option>
                    <option value="divide">/</option>
                </select>
            </div>
        </div>
        <div class="result">
            <div class="result__skew-container">
                <div class="result__skew-container__content">
                    <h2 class="result__title">Resultado: <b>{{ state.result }}</b></h2>
                </div>
            </div>
        </div>
    </div>
</template>


<script setup>
import { reactive, watch } from 'vue';
import './styles.scss';

const state = reactive({
    num1: 0,
    num2: 0,
    operation: 'add',
    result: 0
});

const calculate = () => {
    switch (state.operation) {
        case 'add':
            state.result = state.num1 + state.num2;
            break;
        case 'subtract':
            state.result = state.num1 - state.num2;
            break;
        case 'multiply':
            state.result = state.num1 * state.num2;
            break;
        case 'divide':
            state.result = state.num2 !== 0 ? state.num1 / state.num2 : 'Erro Divisão por Zero';
            break;

    }
}

watch([() => state.num1, () => state.num2, () => state.operatio], calculate)


</script>
