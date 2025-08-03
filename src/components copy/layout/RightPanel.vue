<template>
  <div class="right-panel">
    <Panel title="告警趋势分析区域">
      <AlarmTrendChart />
      <ProcessingEfficiency/>
      <HotspotAnalysis/>
      <PredictiveAnalysis/>
    </Panel>
  </div>
</template>

<script setup>
import Panel from '../common/Panel.vue';
import AlarmTrendChart from '../charts/AlarmTrendChart.vue';
import ProcessingEfficiency from '../modules/ProcessingEfficiency.vue';
import HotspotAnalysis from '../modules/HotspotAnalysis.vue';
import PredictiveAnalysis from '../modules/PredictiveAnalysis.vue';
</script>

<style lang="scss" scoped>
.right-panel {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>