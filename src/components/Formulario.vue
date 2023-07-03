<script setup>
const props = defineProps(['editaNumero1', 'editaNumero2', 'editaOperacao', 'realizarOperacao'])
</script>
<template>
    <form>
        <div class="row text-center align-items-center mt-4">
            <div class="col-4 col-md-2">
                <input type="number" required class="form-control" @change="editaNumero1">
            </div>
            <div class="col-4 col-md-2">
                <input type="number" required class="form-control" @change="editaNumero2">
            </div>
            <div class="col-1 col-md-1">
                <p class="m-0 d-flex"> = </p>
            </div>
            <div class="col-2 col-md-2">
                <p class="m-0 d-flex">{{ realizarOperacao }}</p>
            </div>
            <div class="col-6 col-md-2">
                <select class="form-control" @change="editaOperacao">
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