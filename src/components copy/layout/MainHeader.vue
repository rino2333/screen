<template>
  <header class="main-header">
    <div class="header-left">
      <a href="#" class="back-link"> << 返回 </a>
      <div class="header-info">
        <span class="weather">大雨 17-28°C</span>
      </div>
    </div>
    <h1 class="main-title">建筑物通信基础设施维护管理平台</h1>
    <div class="header-right">
       <span class="date-time">{{ currentTime }}</span>
       <nav class="main-nav">
          <a href="#" class="nav-item">监控总览</a>
          <a href="#" class="nav-item">资产总览</a>
          <a href="#" class="nav-item active">告警监控</a>
          <a href="#" class="nav-item">视频监控</a>
       </nav>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const currentTime = ref('');
const updateTime = () => {
  const now = new Date('2021-12-02T15:20:33'); // 使用图片中的固定时间
  const year = now.getFullYear();
  const month = (now.getMonth() + 1).toString().padStart(2, '0');
  const day = now.getDate().toString().padStart(2, '0');
  const week = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'][now.getDay()];
  const hours = now.getHours().toString().padStart(2, '0');
  const minutes = now.getMinutes().toString().padStart(2, '0');
  currentTime.value = `${year}.${month}.${day} ${week} ${hours}:${minutes}`;
};

onMounted(updateTime);
</script>

<style lang="scss" scoped>
.main-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 70px;
  color: #fff;
  background: linear-gradient(to bottom, rgba(10,25,50,0.5), transparent);
  padding: 0 1rem;
  position: relative;

  .main-title {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    font-size: 1.8rem;
    font-weight: bold;
    color: #fff;
    letter-spacing: 2px;
    text-shadow: 0 0 10px #00aaff;
  }
  
  .header-left, .header-right {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    font-size: 0.9rem;
  }
  
  .back-link {
    color: #00aaff;
    text-decoration: none;
    font-size: 1rem;
  }
  
  .date-time {
    min-width: 210px;
  }

  .main-nav {
    display: flex;
    .nav-item {
      color: #c0c0c0;
      text-decoration: none;
      padding: 0.5rem 1rem;
      border: 1px solid transparent;
      transition: all 0.3s ease;
      background-color: rgba(0, 120, 200, 0.3);
      margin-left: 0.5rem;
      border-radius: 4px;

      &.active, &:hover {
        background-color: rgba(0, 170, 255, 0.5);
        border-color: #00aaff;
        color: #fff;
      }
    }
  }
}
</style>