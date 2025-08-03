<template>
  <div class="time-dist-container">
    <div class="section-title">时间分布</div>
    <div class="card-group">
      <div class="info-card" v-for="item in timeData" :key="item.label">
        <div class="label">{{ item.label }}</div>
        <div class="value">{{ item.value }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const timeData = ref([
    { label: '今日告警', value: 12 },
    { label: '本周告警', value: 51 },
    { label: '本月告警', value: 190 },
    { label: '历史告警', value: 3541 },
]);
</script>

<style lang="scss" scoped>
.time-dist-container {
  margin-top: 1rem;
}
.card-group {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0.5rem;
    .info-card {
        background-color: #1a3e6b;
        padding: 0.5rem;
        text-align: center;
        border-radius: 4px;
        .label {
            font-size: 0.8rem;
            margin-bottom: 0.3rem;
        }
        .value {
            font-size: 1.5rem;
            color: #fff;
            font-weight: bold;
        }
    }
}
</style>