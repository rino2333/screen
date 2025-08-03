<template>
  <div class="center-panel">
    <AlarmMap/>
    <RealtimeAlarms/>
  </div>
</template>

<script setup>
import AlarmMap from '../modules/AlarmMap.vue';
import RealtimeAlarms from '../modules/RealtimeAlarms.vue';
</script>

<style lang="scss" scoped>
.center-panel {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  // 给定一个高度，让内部元素可以百分比计算
  height: calc(100vh - 70px - 2rem);
  .alarm-map {
    height: 55%;
  }
  .realtime-alarms {
    height: 45%;
  }
}
</style>