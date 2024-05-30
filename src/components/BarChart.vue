<template>
    <canvas ref="barChart"></canvas>
  </template>
  
  <script>
  import { onMounted, ref } from 'vue';
  import {
    Chart,
    BarController,
    BarElement,
    LinearScale,
    Title,
    CategoryScale
  } from 'chart.js';
  
  Chart.register(BarController, BarElement, LinearScale, Title, CategoryScale);
  
  export default {
    name: 'BarChart',
    setup() {
      const barChart = ref(null);
  
      onMounted(() => {
        const ctx = barChart.value.getContext('2d');
        new Chart(ctx, {
          type: 'bar',
          data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
            datasets: [{
              label: 'Recent Marketing',
              data: [5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60],
              backgroundColor: 'rgba(153, 102, 255, 0.6)',
              borderColor: 'rgba(153, 102, 255, 1)',
              borderWidth: 1,
            }]
          },
          options: {
            responsive: true,
          }
        });
      });
  
      return {
        barChart
      };
    }
  }
  </script>
  