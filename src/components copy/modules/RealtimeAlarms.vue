<template>
  <Panel title="告警实时展示区域" class="realtime-alarms">
    <div class="alarm-table">
      <table>
        <thead>
          <tr>
            <th>告警时间</th>
            <th>告警级别</th>
            <th>告警内容</th>
            <th>处理状态</th>
            <th>操作</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="alarm in alarms" :key="alarm.id">
            <td>{{ alarm.time }}</td>
            <td><span :class="['level-tag', alarm.levelClass]">{{ alarm.level }}</span></td>
            <td>{{ alarm.content }}</td>
            <td>{{ alarm.status }}</td>
            <td>
              <a href="#" class="action-link">处理进度</a>
              <a href="#" class="action-link">详情</a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </Panel>
</template>

<script setup>
import { ref } from 'vue';
import Panel from '../common/Panel.vue';

const alarms = ref([
  { id: 1, time: '2059/01/17 15:35', level: '重要告警', levelClass: 'level-important', content: '君子食无求饱，居无求安...', status: '未处理' },
  { id: 2, time: '2059/01/17 15:35', level: '紧急告警', levelClass: 'level-urgent', content: '君子食无求饱，居无求安...', status: '处理中' },
  { id: 3, time: '2059/01/17 15:35', level: '重要告警', levelClass: 'level-important', content: '君子食无求饱，居无求安...', status: '处理中' },
  { id: 4, time: '2059/01/17 15:35', level: '重要告警', levelClass: 'level-important', content: '君子食无求饱，居无求安...', status: '处理中' },
  { id: 5, time: '2059/01/17 15:35', level: '重要告警', levelClass: 'level-important', content: '君子食无求饱，居无求安...', status: '处理中' },
]);
</script>

<style lang="scss" scoped>
@import '@/assets/styles/main.scss';

.alarm-table {
  height: 100%;
  overflow-y: auto;
  table {
    width: 100%;
    border-collapse: collapse;
    th, td {
      padding: 0.6rem;
      text-align: left;
      border-bottom: 1px solid #1A3E6B;
      font-size: 0.9rem;
      white-space: nowrap;
    }
    th {
      color: #fff;
      font-weight: normal;
      background-color: rgba(29, 90, 142, 0.3);
      position: sticky;
      top: 0;
    }
    .level-tag {
      padding: 0.2rem 0.5rem;
      border-radius: 4px;
      color: #fff;
      font-size: 0.8rem;
      &.level-urgent { background-color: $urgentColor; }
      &.level-important { background-color: $importantColor; }
    }
    .action-link {
      color: #40A9FF;
      text-decoration: none;
      margin-right: 0.8rem;
      &:hover { text-decoration: underline; }
    }
  }
}
</style>