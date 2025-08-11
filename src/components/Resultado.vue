<script setup>
    const props = defineProps(['number1', 'number2', 'operador', 'calcular'])
</script>

<template>
    <div class="result">
        <h3 class="mt-5">Resultado</h3>
        <h5 class="mt-5 fw-normal text-secondary">{{ props.number1 }} {{ props.operador }} {{ props.number2 }} =
            <span class="fw-bolder text-success">{{ props.calcular }}</span></h5>
    </div>
</template>