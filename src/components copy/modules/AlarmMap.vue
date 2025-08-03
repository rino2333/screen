<template>
  <Panel title="告警地图区域" class="alarm-map">
    <div class="map-container">
      <!-- 这是一个地图的静态背景图 -->
      <div class="map-legend">
        <div v-for="item in legend" :key="item.name" class="legend-item">
          <span class="icon" :style="{ '--color': item.color }"></span>
          {{ item.name }}
        </div>
      </div>
    </div>
  </Panel>
</template>

<script setup>
import { ref } from 'vue';
import Panel from '../common/Panel.vue';

const legend = ref([
    { name: '一般告警', color: '#13C2C2' },
    { name: '重要告警', color: '#f2c94c' },
    { name: '提示告警', color: '#2d8cf0' },
    { name: '紧急告警', color: '#e64242' },
]);
</script>

<style lang="scss" scoped>
.map-container {
  height: 100%;
  background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100"><defs><pattern id="p" width="100" height="100" patternUnits="userSpaceOnUse"><path d="M0 50 H100 M50 0 V100" stroke="%231A3E6B" stroke-width="1"/></pattern></defs><rect width="100%" height="100%" fill="url(%23p)"/></svg>'), #030f23;
  position: relative;
}
.map-legend {
    position: absolute;
    bottom: 1rem;
    left: 1rem;
    background-color: rgba(10, 25, 50, 0.7);
    padding: 0.5rem 1rem;
    border-radius: 4px;
    display: flex;
    gap: 1.5rem;
    .legend-item {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        .icon {
            width: 12px;
            height: 12px;
            background-color: var(--color);
            transform: rotate(45deg);
        }
    }
}
</style>