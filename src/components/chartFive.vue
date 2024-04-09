<template>
  <div class="w-[50%] min-w-[400px] h-[400px]" >
    <canvas
      ref="myChart5" 
      id="myChart5"
      width="20" 
      height="10"
    >
    </canvas>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';

const myChart5 = ref(null)

onMounted(() => {
  new Chart(myChart5.value, {
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
      animations: {
        tension: {
          duration: 1000,
          easing: 'easeInCirc',
          type: 'number',
          from: 1,
          to: 0,
          loop: true,
        },
        color: {
          type: 'color',
          properties: ['borderColor', 'backgroundColor'],
          from: '#00FF00',
          to: '#0000FF',
        }
      },
      scales: {
        y: { // defining min and max so hiding the dataset does not change scale range
          min: 0,
          max: 20
        }
      }
    }
  });
})
</script>