<script setup>
    const props = defineProps(['number1', 'operador', 'number2', 'sinalOperador'])
</script>

<template>
    <form class="form">
        <div class="row p-2 mt-5 bg-success rounded-4">
            <div class="col">
                <input @keyup="props.number1"
                    class="h-100 pt-4 pb-4 text-center form-control" type="number" placeholder="Digite um número">
            </div>
            <div class="col">
                <h5 class="h-100 fw-bolder d-flex align-items-center justify-content-center">{{ props.sinalOperador }}</h5>
            </div>
            <div class="col">
                <input @keyup="props.number2"
                    class="h-100 pt-4 pb-4 text-center form-control" type="number" placeholder="Digite um número:">
            </div>
        </div>
        <div class="row">
            <div class="col">
                <select @change="props.operador" class="mt-5 text-center rounded form-select">
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
</template>