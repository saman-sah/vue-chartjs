<template>
  <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart2" 
        id="myChart2"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';

const myChart2 = ref(null)
const data = [
  { year: 2010, count: 10 },
  { year: 2011, count: 20 },
  { year: 2012, count: 15 },
  { year: 2013, count: 25 },
  { year: 2014, count: 22 },
  { year: 2015, count: 30 },
  { year: 2016, count: 28 },
];
onMounted(() => {
  new Chart(myChart2.value, {
    type: 'bar',
    data: {
      labels: data.map(row => row.year),
      datasets: [{
        label: '# of Votes',
        data: data.map(row => row.count),
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
