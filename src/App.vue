<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

  const estado = reactive({
    number1: 0,
    number2: 0,
    operador: "+",
  })


  const calcular = () => {
    const { operador, number1, number2 } = estado;

    switch (operador) {
      case "+":
        return number1 + number2;
      case "-":
        return number1 - number2;
      case "*":
        return number1 * number2;
      case "/":
        if (number2 !== 0) {
          return number1 / number2;
        }else {
          return "Não é possível dividir por zero"
        }
      case "%":
        if (number2 !== 0) {
          return number1 % number2;
        }else {
          return "Não é possível dividir por zero"
        }
      case "^":
        return number1 ** number2;
    }
  }

</script>

<template>
  <div class="container p-5 mt-4 text-center bg-light rounded-4">
    <Cabecalho />
    <Formulario :number1 = "evento => estado.number1 = Number(evento.target.value)" :number2="evento => estado.number2 = Number(evento.target.value)" :operador="evento => estado.operador = evento.target.value" :sinal-operador="estado.operador"/>
    <Resultado :number1="estado.number1" :number2="estado.number2" :operador="estado.operador" :calcular="calcular()" />
  </div>  
</template>

<style scoped>

</style>
