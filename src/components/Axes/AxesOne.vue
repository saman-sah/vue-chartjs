<template>
  <div class="w-[50%] min-w-[400px] h-[400px]" >
    <canvas
      ref="axesOne" 
      id="axesOne"
      width="20" 
      height="10"
    >
    </canvas>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';

const axesOne = ref(null)

onMounted(() => {
new Chart(axesOne.value, {
  type: 'line',
  data: {
    labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
    datasets: [{
      label: 'Axes - logarithmic',
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
      },
      myScale: {
        type: 'logarithmic',
        position: 'right', // `axis` is determined by the position as `'y'`
      }
    }
  },
});
})
</script>