<template>
  <div class="alarm-level-container">
    <div class="section-title">级别分布</div>
    <div class="alarm-level-list">
      <div v-for="item in alarmLevels" :key="item.name" class="alarm-level-item">
        <span class="level-name">{{ item.name }}</span>
        <div class="progress-bar">
          <div class="progress" :style="{ width: item.percentage + '%', background: item.color }"></div>
        </div>
        <span class="level-count">{{ item.count }}个</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const alarmLevels = ref([
  { name: '紧急告警', count: 116, percentage: 50.4, color: '#e64242' },
  { name: '重要告警', count: 215, percentage: 93.4, color: '#f2c94c' },
  { name: '一般告警', count: 215, percentage: 70, color: '#2d8cf0' },
  { name: '提示告警', count: 215, percentage: 70, color: '#13C2C2' },
]);
</script>

<style lang="scss" scoped>
@import '@/assets/styles/main.scss';
.alarm-level-container {
  margin-bottom: 1.5rem;
}
.alarm-level-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  .alarm-level-item {
    display: grid;
    grid-template-columns: 60px 1fr 50px;
    align-items: center;
    gap: 0.8rem;
    font-size: 0.9rem;
    .progress-bar {
      height: 10px;
      background-color: #1A3E6B;
      border-radius: 5px;
      .progress { height: 100%; border-radius: 5px; }
    }
    .level-count { text-align: right; color: #fff; font-weight: bold; }
  }
}
</style>