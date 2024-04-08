<template>
  <div class="w-[50%] min-w-[400px] h-[400px]" >
      <canvas
        ref="myChart4" 
        id="myChart4"
        width="20" 
        height="10"
      >
      </canvas>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto';
const myChart4 = ref(null)
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
    height:22,
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
    width: 60,
    height: 60,
    count: 14
  },
  { 
    year: 2010, 
    width: 1,
    height: 1,
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
    width: 31,
    height: 16,
    count: 16
  },
  { 
    year: 2016, 
    width: 19,
    height: 25,
    count: 11
  },
  { 
    year: 2018,
    width: 21,
    height: 2,
    count: 17
  },
  { 
    year: 2020, 
    width: 31,
    height: 38,
    count: 8
  },
  { 
    year: 2022, 
    width: 45,
    height: 60,
    count: 1
  },
  { 
    year: 2010, 
    width: 4,
    height: 20,
    count: 3
  },
  { 
    year: 2012, 
    width: 10,
    height: 26,
    count: 7
  },
  { 
    year: 2014, 
    width: 52,
    height: 21,
    count: 4
  },
  { 
    year: 2016, 
    width: 32,
    height: 17,
    count: 14
  },
  { 
    year: 2018,
    width: 32,
    height: 21,
    count: 12
  },
  { 
    year: 2020, 
    width: 26,
    height: 42,
    count: 10
  },
  { 
    year: 2022, 
    width: 22,
    height: 30,
    count: 1
  },
];
onMounted(() => {
  new Chart(myChart4.value, {
    type: 'bubble',
    data: {
      labels: data.map(row => row.year),
      datasets: [
        {
          label: 'width = height',
          data: data
            .filter(row => row.width === row.height)
            .map(row => ({
              x: row.width,
              y: row.height,
              r: row.count
            })),
            borderWidth: 1,
            borderColor: '#FF6384',
            backgroundColor: '#00FF00',
        },
        {
          label: 'width < height',
          data: data
            .filter(row => row.width < row.height)
            .map(row => ({
              x: row.width,
              y: row.height,
              r: row.count
            })),
            borderWidth: 1,
            borderColor: '#FF6384',
            backgroundColor: '#0000FF',
        },
        {
          label: 'Dimention',
          data: data.map(row => ({
            x: row.width,
            y: row.height,
            r: row.count
          })),
          borderWidth: 1,
          borderColor: '#FF6384',
          backgroundColor: '#FFB1C1',
        }
      ]
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
