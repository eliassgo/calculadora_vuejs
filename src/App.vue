<script setup>

import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';


const estado = reactive({
  select: 'operacao',
  numero1: 0,
  numero2: 0,
})

const realizarOperacao = () => {
  const { select } = estado;

  switch (select) {
    case 'somar':
      const soma = estado.numero1 + estado.numero2;
      return soma;
    case 'subtrair':
      const subtrair = estado.numero1 - estado.numero2;
      return subtrair;
    case 'multiplicar':
      const multiplicao = estado.numero1 * estado.numero2;
      return multiplicao;
    case 'dividir':
      if (estado.numero2 !== 0) {
        const divisao = estado.numero1 / estado.numero2;
        return divisao;
      } else {
        alert("Não é possível efetuar divisão por zero")
        return null;
      }
    default:
      return '';
  }
}

</script>

<template>
  <div class="container p-0">
    <Cabecalho />
    <Formulario :edita-numero1="evento => estado.numero1 =
      Number(evento.target.value)" :edita-numero2="evento => estado.numero2 = Number(evento.target.value)"
      :edita-operacao="evento => estado.select = evento.target.value" :realizar-operacao="realizarOperacao()" />
  </div>
</template>

<style scoped>
.container {
  height: 100vh;
  background-color: #ccc;
}
</style>
