<script setup>
import { reactive } from 'vue';

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
    <header>
      <h1>Calculadora aritmética com Vue</h1>
    </header>
    <form>
      <div class="row p-2 mt-5 bg-success rounded-4">
        <div class="col">
          <input @keyup="evento => estado.number1 = Number(evento.target.value)" class="h-100 pt-4 pb-4 text-center" type="number" placeholder="Digite um número">
        </div>
        <div class="col">
          <h5 class="h-100 fw-bolder d-flex align-items-center justify-content-center">{{ estado.operador }}</h5>
        </div>
        <div class="col">
          <input @keyup="evento => estado.number2 = Number(evento.target.value)" class="h-100 pt-4 pb-4 text-center" type="number" placeholder="Digite um número:">
        </div>
      </div>
      <div class="row">
        <div class="col">
          <select @change="evento => estado.operador = evento.target.value" class="mt-5 text-center rounded ">
            <option value="+">Adição (+)</option>
            <option value="-">Subtração (-)</option>
            <option value="*">Multiplicação (*)</option>
            <option value="/">Divisão (/)</option>
            <option value="%">Resto da divisão (%)</option>
            <option value="^">Exponencial (^)</option>
          </select>
        </div>
      </div>
    </form>
    <div class="result">
      <h3 class="mt-5">Resultado</h3>
      <h5 class="mt-5 fw-normal text-secondary">{{ estado.number1 }} {{ estado.operador }} {{ estado.number2 }} = <span class="fw-bolder text-success">{{ calcular() }}</span></h5>
    </div>
  </div>  
</template>

<style scoped>

</style>
