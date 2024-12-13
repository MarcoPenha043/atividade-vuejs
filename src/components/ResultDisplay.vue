<template>
    <div class="result-display">
        <h2>{{ resultado }}</h2>
    </div>
</template>

<script setup>
defineProps({
    resultado: [String, Number]
});
</script>

<style scoped>
.result-display {
    font-size: 24px;
    font-weight: bold;
    color: #333;
    margin-top: 20px;
    padding: 15px;
    border-radius: 15px;
    background-color: #e9ecef;
    border: 2px solid #ddd;
    max-width: 300px;
    margin: 0 auto;
    transition: all 0.3s ease;
}

.result-display h2 {
    margin: 0;
    font-size: 28px;
}

.result-display:hover {
    background-color: #dfe4ea;
    transform: scale(1.05);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}
</style>