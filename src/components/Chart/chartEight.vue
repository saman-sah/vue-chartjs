<template>
    <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart8" 
        id="myChart8"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';

const myChart8 = ref(null)

onMounted(() => {
  new Chart(myChart8.value, {
    type: 'line',
    data: {
        datasets: [{
            type: 'bar',
            label: 'Bar Dataset',
            data: [10, 40, 20, 50],
            order: 2
        }, {
            type: 'line',
            label: 'Line Dataset',
            data: [10, 40, 20, 50],
            order: 1
        }],
        labels: ['January', 'February', 'March', 'April']
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