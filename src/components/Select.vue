<script setup>
    const props = defineProps(['mathOp']);
</script>

<template>
    <select @change="mathOp($event)">
        <option value="plus">Adição</option>
        <option value="minus">Subtração</option>
        <option value="divide">Divisão</option>
        <option value="x">Multiplicação</option>
    </select>
</template>

<style scoped>

    select{
        border-radius: 10px;
        border: solid 1.5px #ccc;
        outline: none;

        color: #34495e;

        width: 100%;

        margin: 10px 0 0 0;
        padding: 10px;

        cursor: pointer;
    }

</style>