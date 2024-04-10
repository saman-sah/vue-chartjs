<template>
  <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart6" 
        id="myChart6"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';
const myChart6 = ref(null)



onMounted(() => {
  new Chart(myChart6.value, {
    type: 'doughnut',
    data: {
      labels: [
        'Red',
        'Blue',
        'Yellow'
      ],
      datasets: [{
        label: 'My First Dataset',
        data: [300, 50, 100],
        backgroundColor: [
          'rgb(255, 99, 132)',
          'rgb(54, 162, 235)',
          'rgb(255, 205, 86)'
        ],
        hoverOffset: 4
      }]
    },
    options: {
      plugins: {
        customCanvasBackgroundColor: {
          color: 'lightGreen',
        }
      }
    },
  });
})
</script>
