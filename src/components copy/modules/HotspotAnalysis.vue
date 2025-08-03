<template>
  <div class="container">
    <div class="section-title">热点分析</div>
    <div class="hotspot-list">
      <div class="hotspot-item">
        <span class="label">告警频发设备</span>
        <span class="value">某某设备</span>
      </div>
      <div class="hotspot-item">
        <span class="label">告警频发区域</span>
        <span class="value">区域一</span>
      </div>
      <div class="hotspot-item">
        <span class="label">告警频发时间段</span>
        <span class="value">21:00-24:00</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  margin-bottom: 1.5rem;
}
.hotspot-list {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
  .hotspot-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgba(29, 90, 142, 0.2);
    padding: 0.5rem 1rem;
    border-left: 3px solid #00aaff;
    .value {
      color: #fff;
      font-weight: bold;
    }
  }
}
</style>