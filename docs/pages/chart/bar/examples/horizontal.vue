<template>
  <div>
    <ev-chart
      :data="chartData"
      :options="chartOptions"
    />
    <br>
  </div>
</template>

<script>

  export default {
    data() {
      return {
        chartData: {
          series: {
            series1: { name: 'series#1' },
            series2: { name: 'series#2' },
            series3: { name: 'series#3' },
            series4: { name: 'series#4' },
          },
          labels: [
            'January',
            'February',
            'March',
            'April',
            'May',
          ],
          data: {
            series1: [100, 150, 50, 150, 350],
            series2: [50, 100, 70, 80, 100],
            series3: [100, 100, 200, 150, 60],
            series4: [100, 80, 100, 150, 50],
          },
        },
        chartOptions: {
          type: 'bar',
          thickness: 0.8,
          width: '100%',
          title: {
            text: 'Title Test',
            show: true,
          },
          legend: {
            show: true,
            position: 'right',
          },
          horizontal: true,
          axesX: [{
            type: 'linear',
            startToZero: true,
            autoScaleRatio: 0.1,
            showGrid: false,
          }],
          axesY: [{
            type: 'step',
            showGrid: false,
          }],
        },
      };
    },
  };
</script>
