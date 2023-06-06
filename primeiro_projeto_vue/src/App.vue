<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';

const estado = reactive({
    num1: 0,
    num2: 0,
    sinal: '+',
    resultado: 0
})

const calculo = () => {
  const { num1, num2, sinal } = estado;

  switch (sinal) {
    case '+':
      return estado.resultado = parseFloat(num1) + parseFloat(num2);
    case '-':
      return estado.resultado = parseFloat(num1) - parseFloat(num2);
    case '*':
      return estado.resultado = parseFloat(num1) * parseFloat(num2);
    case '/':
      return estado.resultado = parseFloat(num1) / parseFloat(num2);
    case '%':
      return estado.resultado = parseFloat(num1) % parseFloat(num2);
    }
}

const alteraNum1 = (evento) => {
  estado.num1 = evento.target.value;
  calculo();
}

const alteraNum2 = (evento) => {
  estado.num2 = evento.target.value;
  calculo();
}

const alteraSinal = (evento) => {
  estado.sinal = evento.target.value;
  calculo();
}
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario :resultado="estado.resultado" :num1="estado.num1" :num2="estado.num2" :sinal="estado.sinal" :alteraNum1="alteraNum1" :alteraNum2="alteraNum2" :alteraSinal="alteraSinal"/>
  </div>
</template>

<style scoped>
</style>
