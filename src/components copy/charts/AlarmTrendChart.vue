<template>
  <div class="chart-container">
    <div class="chart-tabs">
        <div class="tab active">告警数量变化</div>
        <div class="tab">不同级别告警</div>
        <div class="tab">不同类型告警</div>
    </div>
    <v-chart class="chart" :option="chartOption" autoresize />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { use } from 'echarts/core';
import { CanvasRenderer } from 'echarts/renderers';
import { LineChart } from 'echarts/charts';
import { GridComponent, TooltipComponent } from 'echarts/components';
import * as echarts from 'echarts';

use([CanvasRenderer, LineChart, GridComponent, TooltipComponent]);

const chartOption = ref({
  tooltip: { trigger: 'axis' },
  grid: { top: '20%', left: '3%', right: '4%', bottom: '3%', containLabel: true },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12'],
    axisLine: { lineStyle: { color: '#2A5C9A' } },
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: '#1A3E6B' } },
    axisLine: { lineStyle: { color: '#2A5C9A' } },
  },
  series: [{
    name: '告警数量',
    type: 'line',
    smooth: true,
    showSymbol: false,
    data: [130, 135, 120, 130, 150, 170, 180, 210, 190, 150, 120, 110, 120],
    lineStyle: { color: '#4dffff' },
    areaStyle: {
      color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
        { offset: 0, color: 'rgba(77, 255, 255, 0.5)' },
        { offset: 1, color: 'rgba(77, 255, 255, 0)' }
      ])
    }
  }]
});
</script>

<style lang="scss" scoped>
.chart-container {
  height: 250px;
}
.chart-tabs {
    display: flex;
    gap: 0.5rem;
    margin-bottom: 1rem;
    .tab {
        padding: 0.3rem 0.8rem;
        background-color: rgba(29, 90, 142, 0.3);
        border: 1px solid #1d5a8e;
        border-radius: 4px;
        cursor: pointer;
        &.active {
            background-color: #1d5a8e;
            color: #fff;
        }
    }
}
.chart {
    height: calc(100% - 40px);
}
</style>