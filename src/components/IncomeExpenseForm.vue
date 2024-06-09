<template>
    <div class="form-container">
      <form @submit.prevent="addRecord">
        <div class="form-group">
          <label for="type">Tipo:</label>
          <select v-model="type" id="type">
            <option value="income">Ingreso</option>
            <option value="expense">Gasto</option>
          </select>
        </div>
        <div class="form-group">
          <label for="amount">Monto:</label>
          <input type="number" v-model="amount" id="amount" required>
        </div>
        <button type="submit">Agregar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        type: 'income',
        amount: 0
      };
    },
    methods: {
      addRecord() {
        this.$emit('add-record', { type: this.type, amount: parseFloat(this.amount) });
        this.amount = 0;
      }
    }
  };
  </script>
  
  <style scoped>
  .form-container {
    margin: 20px;
  }
  .form-group {
    margin-bottom: 10px;
  }
  label {
    margin-right: 10px;
  }
  button {
    background-color: #42b983;
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
  }
  button:hover {
    background-color: #369973;
  }
  </style>
  