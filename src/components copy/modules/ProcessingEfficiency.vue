<template>
  <div class="container">
    <div class="section-title">处理效率</div>
    <div class="card-group">
      <div class="efficiency-card">
        <div class="label">平均处理时间</div>
        <div class="value">38<span class="unit">分钟</span></div>
      </div>
       <div class="efficiency-card">
        <div class="label">处理成功率</div>
        <div class="value">86<span class="unit">%</span></div>
      </div>
       <div class="efficiency-card">
        <div class="label">响应时间趋势</div>
        <div class="value">14<span class="unit">分钟</span></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  margin-top: 1.5rem;
  margin-bottom: 1.5rem;
}
.card-group {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    .efficiency-card {
        background-color: rgba(29, 90, 142, 0.4);
        padding: 1rem;
        text-align: center;
        border-radius: 4px;
        .label {
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }
        .value {
            font-size: 1.8rem;
            color: #fff;
            font-weight: bold;
            .unit {
                font-size: 0.9rem;
                margin-left: 0.3rem;
                color: #c0c0c0;
            }
        }
    }
}
</style>