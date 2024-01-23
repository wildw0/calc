<script setup>
  import { reactive } from 'vue';
  import Header1 from './components/Header1.vue'
  import Form1 from './components/Form1.vue'
  import Result from './components/Result.vue'
  

  const state = reactive({
  filtro: '',
  num1: '',
  num2: '',
  resultado: '',
})

const soma = () => {
  const resultadoSoma = state.num1 + state.num2
  state.resultado = resultadoSoma;
  return state.resultado
}

const subtracao = () => {
  const resultadoSubtracao = state.num1 - state.num2
  state.resultado = resultadoSubtracao;
  return state.resultado
}

const multiplicacao = () => {
  const resultadoMultiplicacao = state.num1 * state.num2
  state.resultado = resultadoMultiplicacao;
  return state.resultado
}

const divisao = () => {
  const resultadoDivisao = state.num1 / state.num2
  state.resultado = resultadoDivisao
  return state.resultado
}
</script>

<template>
  <div class="container">
    <Header1 />
    <div class="row">
      <div class="d-inline-flex">
        <Form1 :firstNumb="event => state.num1 = Number(event.target.value)" :secondNumb="event => state.num2 = Number(event.target.value)" :selectOpera="state.filtro" />
        <Result :selectOpera="state.filtro" :funcSoma="soma()" :funcSub="subtracao()" :funcMult="multiplicacao()" :funcDivisao="divisao()" />
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
