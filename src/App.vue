<script setup>

</script>

<template>
  <div class="container p-5 mt-4 text-center bg-light rounded-4">
    <header>
      <h1>Calculadora aritmética com Vue</h1>
    </header>
    <div class="row p-2 mt-5 bg-success rounded-4">
      <div class="col">
        <input class="h-100 pt-4 pb-4 text-center" type="number" placeholder="Digite um número">
      </div>
      <div class="col">
        <h5 class="h-100 fw-bolder d-flex align-items-center justify-content-center">+</h5>
      </div>
      <div class="col">
        <input class="h-100 pt-4 pb-4 text-center" type="number" placeholder="Digite um número:">
      </div>
    </div>
    <div class="row">
      <div class="col">
        <select class="mt-5 text-center rounded ">
          <option value="adicionar">Adição (+)</option>
          <option value="subtrair">Subtração (-)</option>
          <option value="multiplicar">Multiplicação (*)</option>
          <option value="dividir">Divisão (/)</option>
          <option value="resto">Resto da divisão (%)</option>
          <option value="elevado">Exponencial (^)</option>
        </select>
      </div>
    </div>
    <div class="result">
      <h3 class="mt-5">Resultado</h3>
      <h5 class="mt-5 fw-normal text-secondary">2 + 2 = <span class="fw-bolder text-success">4</span></h5>
    </div>
  </div>  
</template>

<style scoped>

</style>
