<template>
    <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart7" 
        id="myChart7"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';

const myChart7 = ref(null)

onMounted(() => {
  new Chart(myChart7.value, {
    type: 'line',
    data: {
      labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
      datasets: [
            {fill: 'origin'},      // 0: fill to 'origin'
            {fill: '+2'},          // 1: fill to dataset 3
            {fill: 1},             // 2: fill to dataset 1
            {fill: false},         // 3: no fill
            {fill: '-2'},          // 4: fill to dataset 2
            {fill: {value: 25}}    // 5: fill to axis value 25
        ]
    },
    options: {
        plugins: {
            filler: {
                propagate: true
            }
        }
    }
  });
})
</script>