<script setup>
    const props = defineProps(['numberInput']);
</script>

<template>
    <input type="number" min="0" required @change="numberInput">
</template>

<style scoped>

    input{
        border-radius: 10px;
        border: solid 1.5px #ccc;
        outline: none;

        width: 50%;
        padding: 10px;

    }

    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }

    input[type=number] {
        -moz-appearance:textfield; /* Firefox */
    }

</style>