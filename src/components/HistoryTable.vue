<template>
    <div class="table-container">
      <table>
        <thead>
          <tr>
            <th>Tipo</th>
            <th>Monto</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(record, index) in records" :key="index">
            <td>{{ record.type }}</td>
            <td>{{ record.amount }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      records: {
        type: Array,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .table-container {
    margin: 20px;
  }
  table {
    width: 100%;
    border-collapse: collapse;
  }
  th, td {
    border: 1px solid #ddd;
    padding: 8px;
  }
  th {
    background-color: #f2f2f2;
  }
  </style>
  