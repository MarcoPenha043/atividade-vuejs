<template>
    <div class="input-fields">
        <input type="number" :value="numero1" @input="$emit('update:numero1', $event.target.value)"
            placeholder="Digite o primeiro número" class="input" />
        <input type="number" :value="numero2" @input="$emit('update:numero2', $event.target.value)"
            placeholder="Digite o segundo número" class="input" />
    </div>
</template>

<script setup>
defineProps({
    numero1: Number,
    numero2: Number
});
</script>

<style scoped>
.input-fields {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-bottom: 20px;
}

.input {
    padding: 15px;
    font-size: 18px;
    width: 100%;
    border-radius: 10px;
    border: 2px solid #ddd;
    background-color: #f8f9fa;
    transition: all 0.3s ease-in-out;
    outline: none;
}

.input:focus {
    border-color: #6a11cb;
    box-shadow: 0 0 10px rgba(106, 17, 203, 0.4);
}

.input::placeholder {
    color: #bbb;
}
</style>