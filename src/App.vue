<template>
  <div id="app">
    <h1>Registro de Ingresos y Gastos</h1>
    <div class="container">
      <IncomeExpenseForm @add-record="addRecord" />
      <HistoryTable :records="records" />
      <ChartArea :records="records" />
    </div>
  </div>
</template>

<script>
import IncomeExpenseForm from './components/IncomeExpenseForm.vue';
import HistoryTable from './components/HistoryTable.vue';
import ChartArea from './components/ChartArea.vue';

export default {
  components: {
    IncomeExpenseForm,
    HistoryTable,
    ChartArea
  },
  data() {
    return {
      records: []
    };
  },
  methods: {
    addRecord(record) {
      this.records.push(record);
    }
  }
};
</script>

<style>
body {
  font-family: 'Arial', sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

#app {
  background: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 90%;
  max-width: 800px;
  text-align: center;
}

h1 {
  color: #333;
  margin-bottom: 20px;
}

.container {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

form {
  display: flex;
  justify-content: space-around;
  gap: 10px;
  margin-bottom: 20px;
}

label {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

input[type="number"], select, button {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin-top: 5px;
  font-size: 16px;
}

button {
  background-color: #42b983;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #38a774;
}

table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  padding: 10px;
  border: 1px solid #ddd;
  text-align: left;
}

th {
  background-color: #f4f4f4;
}

.chart-container {
  width: 100%;
  height: 400px;
}
</style>
