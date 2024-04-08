<template>
    <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart" 
        id="myChart"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';

const myChart = ref(null)

onMounted(() => {
  new Chart(myChart.value, {
    type: 'line',
    data: {
      labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
      datasets: [{
        label: '# of Votes',
        data: [12, 19, 3, 5, 2, 3],
        borderWidth: 1,
        borderColor: '#FF6384',
        backgroundColor: '#FFB1C1',
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  });
})
</script>