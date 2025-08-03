<template>
  <div class="chart-container">
    <div class="section-title">类型统计</div>
    <v-chart class="chart" :option="chartOption" autoresize />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { use } from 'echarts/core';
import { CanvasRenderer } from 'echarts/renderers';
import { LineChart } from 'echarts/charts';
import { GridComponent, TooltipComponent, LegendComponent } from 'echarts/components';

use([CanvasRenderer, LineChart, GridComponent, TooltipComponent, LegendComponent]);

const chartOption = ref({
  color: ['#13C2C2', '#2d8cf0', '#f2c94c', '#e64242'],
  tooltip: { trigger: 'axis' },
  legend: {
    data: ['设备故障', '网络异常', '环境告警', '系统告警'],
    textStyle: { color: '#c0c0c0' },
    top: '0%',
    right: '5%',
    itemWidth: 15,
    itemHeight: 10,
  },
  grid: { left: '3%', right: '4%', bottom: '3%', containLabel: true },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: ['1','2','3','4','5','6','7','8','9','10','11','12'],
    axisLine: { lineStyle: { color: '#2A5C9A' } },
  },
  yAxis: {
    type: 'value',
    splitLine: { show: true, lineStyle: { color: '#1A3E6B' } },
    axisLine: { lineStyle: { color: '#2A5C9A' } },
  },
  series: [
    { name: '设备故障', type: 'line', smooth: true, data: [90, 110, 160, 125, 130, 115, 160, 150, 140, 120, 130, 110] },
    { name: '网络异常', type: 'line', smooth: true, data: [95, 120, 130, 110, 120, 105, 110, 160, 180, 200, 190, 205] },
    { name: '环境告警', type: 'line', smooth: true, data: [60, 70, 75, 100, 120, 150, 165, 160, 100, 105, 140, 150] },
    { name: '系统告警', type: 'line', smooth: true, data: [30, 60, 80, 70, 50, 55, 98, 80, 85, 100, 102, 60] },
  ]
});
</script>

<style lang="scss" scoped>
.chart-container {
  height: 250px;
  margin-bottom: 1.5rem;
  .chart {
    height: calc(100% - 30px);
    width: 100%;
  }
}
</style>