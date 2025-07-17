<script setup>
    const props = defineProps([]);
</script>

<template>
    <div class="card-body">
        <div class="row mb-3 mt-5">
            <div class="col-md-4">
                <input class="form-control" type="number" :value="estado.num1" @input="evento => estado.num1 = Number(evento.target.value)" placeholder="Digite o primeiro número">
            </div>

            <div class="col-md-4">
                <select class="form-select text-center" :value="estado.operacao" @change="evento => estado.operacao = evento.target.value">
                    <option value="--">Selecione o operador</option>
                    <option value="somar">SOMAR POR</option>
                    <option value="diminuir">DIMINUIR POR</option>
                    <option value="dividir">DIVIDIR POR</option>
                    <option value="multiplicar">MULTIPLICAR POR</option>
                </select>
            </div>

            <div class="col-md-4">
                <input class="form-control" type="number" :value="estado.num2" @input="evento => estado.num2 = Number(evento.target.value) " placeholder="Digite o segundo número">
            </div>
        </div>
        <div class="text-center mt-5">
            <p v-if="estado.erro" class="text-danger fw-bold">{{ estado.erro }}</p>
            <h4>Resultado: {{calcularResultado()}}</h4>
        </div>          
    </div>
</template>

<style scoped>
    .card-body {
        background-color: #ddd;
    }
</style>