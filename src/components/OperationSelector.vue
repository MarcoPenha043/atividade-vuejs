<template>
    <div class="operation-selector">
        <select :value="operacao" @change="$emit('update:operacao', $event.target.value)" class="select">
            <option value="+">Soma</option>
            <option value="-">Subtração</option>
            <option value="*">Multiplicação</option>
            <option value="/">Divisão</option>
        </select>
    </div>
</template>

<script setup>
defineProps({
    operacao: String
});
</script>

<style scoped>
.operation-selector {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
}

.select {
    padding: 15px;
    font-size: 18px;
    width: 100%;
    max-width: 200px;
    border-radius: 10px;
    border: 2px solid #ddd;
    background-color: #f8f9fa;
    transition: all 0.3s ease-in-out;
    outline: none;
}

.select:focus {
    border-color: #6a11cb;
    box-shadow: 0 0 10px rgba(106, 17, 203, 0.4);
}

.select option {
    padding: 10px;
}
</style>