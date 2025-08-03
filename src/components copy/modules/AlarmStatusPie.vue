<template>
  <div class="status-container">
    <div class="section-title">状态分布</div>
    <div class="status-content">
      <div class="pie-chart-wrapper">
        <v-chart class="chart" :option="chartOption" autoresize />
      </div>
      <div class="legend">
        <div class="legend-item" v-for="item in data" :key="item.name">
          <span class="dot" :style="{backgroundColor: item.color}"></span>
          {{ item.name }}
          <span class="value">{{ item.value }}个</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { use } from 'echarts/core';
import { CanvasRenderer } from 'echarts/renderers';
import { PieChart } from 'echarts/charts';
import { TooltipComponent, LegendComponent } from 'echarts/components';

use([CanvasRenderer, PieChart, TooltipComponent, LegendComponent]);

const data = ref([
    { value: 215, name: '未处理', color: '#f2c94c' },
    { value: 215, name: '处理中', color: '#13C2C2' },
    { value: 215, name: '已处理', color: '#2d8cf0' },
    { value: 215, name: '已关闭', color: '#1a5e8a' },
]);

const chartOption = ref({
    tooltip: { trigger: 'item' },
    series: [{
        type: 'pie',
        radius: ['60%', '80%'],
        avoidLabelOverlap: false,
        label: { show: false },
        labelLine: { show: false },
        data: data.value.map(item => ({
            value: item.value,
            name: item.name,
            itemStyle: { color: item.color }
        })),
    }],
});
</script>

<style lang="scss" scoped>
.status-container {
  margin-bottom: 1.5rem;
}
.status-content {
  display: flex;
  align-items: center;
  gap: 1rem;
  height: 100px;
}
.pie-chart-wrapper {
  width: 100px;
  height: 100px;
}
.legend {
  flex-grow: 1;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.8rem;
  .legend-item {
    display: flex;
    align-items: center;
    .dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      margin-right: 8px;
    }
    .value {
      margin-left: auto;
      color: #fff;
      font-weight: bold;
    }
  }
}
</style>