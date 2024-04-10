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

onMounted(() => {
  new Chart(myChart2.value, {
    type: 'bar',
    data: {
    datasets: [{
      yAxisID: 'yAxis'
    }]
  },

    options: {
      scales: {
        // xAxis: {
        //   // The axis for this scale is determined from the first letter of the id as `'x'`
        //   // It is recommended to specify `position` and / or `axis` explicitly.
        //   type: 'time',
        // }
      }
    }
  });
})
</script>
