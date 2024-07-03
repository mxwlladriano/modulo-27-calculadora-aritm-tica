<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add'
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.num1 + this.num2;
        case 'subtract':
          return this.num1 - this.num2;
        case 'multiply':
          return this.num1 * this.num2;
        case 'divide':
          return this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
};
</script>

<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="input-group">
      <label for="num1">Número 1:</label>
      <input type="number" v-model.number="num1" id="num1">
    </div>
    <div class="input-group">
      <label for="num2">Número 2:</label>
      <input type="number" v-model.number="num2" id="num2">
    </div>
    <div class="input-group">
      <label for="operation">Operação:</label>
      <select v-model="operation" id="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
    </div>
    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #f9f9f9;
}

h1 {
  font-size: 24px;
  margin-bottom: 20px;
  color: #333;
}

.input-group {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin-bottom: 15px;
}

label {
  font-size: 16px;
  margin-bottom: 5px;
  color: #555;
}

input[type="number"],
select {
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
  outline: none;
  width: 100%;
}

input[type="number"]:focus,
select:focus {
  border-color: #66afe9;
  box-shadow: 0 0 8px rgba(102, 175, 233, 0.6);
}

.result {
  margin-top: 20px;
}

.result h2 {
  font-size: 20px;
  color: #333;
}
</style>
