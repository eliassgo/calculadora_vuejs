<script setup>
const props = defineProps(['editaNumero1', 'editaNumero2', 'editaOperacao', 'realizarOperacao'])
</script>
<template>
    <form>
        <div class="row text-center align-items-center mt-4 p-5">
            <div class="col-4 col-md-2 mb-5 m-md-0">
                <input type="number" required class="form-control" @change="editaNumero1">
            </div>
            <div class="col-4 col-md-2 mb-5 m-md-0">
                <input type="number" required class="form-control" @change="editaNumero2">
            </div>
            <div class="col-1 col-md-1 mb-5 m-md-0">
                <p class="m-0 d-flex fs-5"> = </p>
            </div>
            <div class="col-2 col-md-2 mb-5 m-md-0">
                <p class="m-0 d-flex fs-5">{{ realizarOperacao }}</p>
            </div>
            <div class="col-6 col-md-2">
                <select class="form-control bg-dark text-white" @change="editaOperacao">
                    <option value="operacao">Operação</option>
                    <option value="somar">Somar</option>
                    <option value="subtrair">Subtrair</option>
                    <option value="dividir">Dividir</option>
                    <option value="multiplicar">Multiplicar</option>
                </select>
            </div>
        </div>
    </form>
</template>
