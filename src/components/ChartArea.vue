<template>
    <div>
      <Bar :chart-data="chartData" :options="chartOptions"></Bar>
    </div>
  </template>
  
  <script>
  import { Bar } from 'vue-chartjs';
  import { Chart, registerables } from 'chart.js';
  
  Chart.register(...registerables);
  
  export default {
    components: {
      Bar
    },
    props: {
      records: {
        type: Array,
        required: true
      }
    },
    computed: {
      chartData() {
        const income = this.records.filter(r => r.type === 'income').reduce((sum, r) => sum + r.amount, 0);
        const expense = this.records.filter(r => r.type === 'expense').reduce((sum, r) => sum + r.amount, 0);
        return {
          labels: ['Ingresos', 'Gastos'],
          datasets: [
            {
              label: 'Monto',
              backgroundColor: ['#42b983', '#ff6384'],
              data: [income, expense]
            }
          ]
        };
      },
      chartOptions() {
        return {
          responsive: true,
          maintainAspectRatio: false
        };
      }
    }
  };
  </script>
  
  <style scoped>
  /* Estilos específicos para este componente */
  </style>
  