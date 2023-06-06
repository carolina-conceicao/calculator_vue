<script setup>
    const props = defineProps(['resultado', 'num1', 'num2', 'sinal', 'alteraNum1', 'alteraNum2', 'alteraSinal'])
</script>

<template>
    <form @submit.prevent>
        <div class="row">
            <div class="col">
                <input :value="props.num1" @change="props.alteraNum1" required type="number" placeholder="Digite um numero"
                    class="form-control">
            </div>
            <div class="col">
                <select class="form-select" :value="props.sinal" @change="props.alteraSinal">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                    <option value="%">%</option>
                </select>
            </div>
            <div class="col">
                <input :value="props.num2" @change="props.alteraNum2" required type="number" placeholder="Digite um numero"
                    class="form-control">
            </div>
        </div>
        <div class="p-4 mb-4 mt-4 bg-light rounded-3 text-center">
            <p class="h3">Resultado:</p>
            <span class="h2">{{ props.resultado }}</span>
        </div>
    </form>
</template>