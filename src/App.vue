<template>
  <div id="app">
    <div class="container">
      <h1>Calculadora Aritmética</h1>
      <InputFields 
        :numero1="numero1" 
        :numero2="numero2" 
        @update:numero1="numero1 = $event"
        @update:numero2="numero2 = $event"
      />
      <OperationSelector 
        :operacao="operacao" 
        @update:operacao="operacao = $event"
      />
      <ResultDisplay :resultado="resultado" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

// Importando os componentes
import InputFields from "./components/InputFields.vue";
import OperationSelector from "./components/OperationSelector.vue";
import ResultDisplay from "./components/ResultDisplay.vue";

// Variáveis reativas
const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref("+");

// Cálculo do resultado
const resultado = computed(() => {
  switch (operacao.value) {
    case "+":
      return numero1.value + numero2.value;
    case "-":
      return numero1.value - numero2.value;
    case "*":
      return numero1.value * numero2.value;
    case "/":
      return numero2.value !== 0
        ? numero1.value / numero2.value
        : "Erro (Divisão por zero)";
    default:
      return "Operação inválida";
  }
});
</script>

<style>

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Roboto', sans-serif;
  text-align: center;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #6a11cb, #2575fc);
}

.container {
  background-color: #ffffff;
  padding: 40px;
  border-radius: 15px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 400px;
}

h1 {
  color: #3a3a3a;
  font-size: 36px;
  margin-bottom: 20px;
  font-weight: bold;
}

@media (max-width: 600px) {
  h1 {
    font-size: 28px;
  }

  .container {
    padding: 20px;
  }
}
</style>