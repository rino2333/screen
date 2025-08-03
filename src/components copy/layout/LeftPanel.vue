<template>
  <div class="left-panel">
    <Panel title="告警统计区域">
      <AlarmLevelBars/>
      <AlarmTypeChart/>
      <AlarmStatusPie/>
      <AlarmTimeDistribution/>
    </Panel>
  </div>
</template>

<script setup>
import Panel from '../common/Panel.vue';
import AlarmLevelBars from '../modules/AlarmLevelBars.vue';
import AlarmTypeChart from '../charts/AlarmTypeChart.vue';
import AlarmStatusPie from '../modules/AlarmStatusPie.vue';
import AlarmTimeDistribution from '../modules/AlarmTimeDistribution.vue';
</script>

<style lang="scss" scoped>
.left-panel {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>