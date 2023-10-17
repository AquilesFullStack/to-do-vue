<script setup>
import { reactive } from 'vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const state = reactive({
    filtro:'soma', 
    num1: '',
    num2: '',
    resultado :'',
})

const soma = () =>{
    const resultadoSoma = state.num1 + state.num2
    state.resultado = resultadoSoma;
    return state.resultado
}

const sub = () => {
    const resultadoSub = state.num1 - state.num2
    state.resultado = resultadoSub
    return state.resultado
}

const mult = () => {
    const resultadoMult = state.num1 * state.num2
    state.resultado = resultadoMult
    return state.resultado
}

const div = () => {
    const resultadoDiv = state.num1 / state.num2
    state.resultado = resultadoDiv
    return  state.resultado
}
</script>

<template >
    <div class="container">
        <Formulario :valorInput1="event => state.num1 = Number(event.target.value)" :valorInput2 = "event => state.num2 = Number(event.target.value)" :filtro="state.filtro" :selecioneFiltro="event =>state.filtro = event.target.value"/>
        <Resultado :filtro="state.filtro" :funcaoSoma="soma()" :funcaoSub="sub()" :funcaoMult="mult()" :funcaoDiv="div()"/>
    </div>
</template>

<style scoped>
.container{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    width: 100vw;
    height: 100vh;
}
</style>
