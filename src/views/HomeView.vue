<template>
  <div class="home">
    <div class="w-[50rem] h-[50rem]" >
      <canvas
        ref="myChart" 
        id="myChart"
        width="20" 
        height="10"
        >
      </canvas>
    </div>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Chart from 'chart.js/auto';

const myChart = ref(null)

onMounted(() => {
  console.log('myChart.value', myChart.value);
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
