<script setup>

import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';

const estado = reactive({
  select: 'operacao',
  numero1: 0,
  numero2: 0,
})

// Funções operações aritméticas 
const somar = () => {
  const soma = Number(estado.numero1) + Number(estado.numero2);
  return soma;
}

const subtrair = () => {
  const subtrair = Number(estado.numero1) - Number(estado.numero2);
  return subtrair;
}
const multiplicao = () => {
  const multiplicao = Number(estado.numero1) * Number(estado.numero2);
  return multiplicao;
}

const divisao = () => {
  if (Number(estado.numero2) !== 0) {
    const divisao = Number(estado.numero1) / Number(estado.numero2);
    return divisao;
  } else {
    alert("Não é possível efetuar divisão por zero")
    return null;
  }
}

// Função para redirecionar a escolha a operação desejada
const realizarOperacao = () => {
  const { select } = estado;

  switch (select) {
    case 'somar':
      const resultadoSoma = somar();
      return resultadoSoma;
    case 'subtrair':
      const resultadoSubtracao = subtrair();
      return resultadoSubtracao;
    case 'multiplicar':
      const resultadoMultiplicacao = multiplicao();
      return resultadoMultiplicacao;
    case 'dividir':
      const resultadoDivisao = divisao();
      return resultadoDivisao;
    default:
      return null;
  }
}

</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario :edita-numero1="evento => estado.numero1 =
      evento.target.value" :edita-numero2="evento => estado.numero2 = evento.target.value"
      :edita-operacao="evento => estado.select = evento.target.value" :realizar-operacao="realizarOperacao()" />
  </div>
</template>

<style scoped></style>
