<template>
  <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart3" 
        id="myChart3"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';
const myChart3 = ref(null)
const data = [
  { 
    year: 2010, 
    
      width: 1,
      height: 2,
      count: 3
     
  },
  { 
    year: 2012, 
    
      width: 12,
      height: 15,
      count: 18
     
  },
  { 
    year: 2014, 
    
      width: 17,
      height: 21,
      count: 34
     
  },
  { 
    year: 2016, 
    
      width: 19,
      height: 25,
      count: 39
     
  },
  { 
    year: 2018, 
    
      width: 22,
      height: 29,
      count: 47
     
  },
  { 
    year: 2020, 
    
      width: 31,
      height: 38,
      count: 54
     
  },
  { 
    year: 2022, 
    
      width: 45,
      height: 60,
      count: 1
     
  },
];
onMounted(() => {
  new Chart(myChart3.value, {
    type: 'bubble',
    data: {
      labels: data.map(row => row.year),
      datasets: [{
        label: 'Dimention',
        data: data.map(row => ({
          x: row.width,
          y: row.height,
          r: row.count
        })),
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
