<template>
  <div class="container">
    <div class="section-title">预测分析</div>
    <div class="card-group">
      <div class="predict-card">
        <div class="label">故障预测</div>
        <div class="value">30<span class="unit">个</span></div>
      </div>
      <div class="predict-card">
        <div class="label">维修预测</div>
        <div class="value">129<span class="unit">个</span></div>
      </div>
      <div class="predict-card">
        <div class="label">更换预测</div>
        <div class="value">27<span class="unit">个</span></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card-group {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    .predict-card {
        background-color: #1a3e6b;
        padding: 0.8rem;
        text-align: center;
        border-radius: 4px;
        border: 1px solid #205D9E;
        .label {
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }
        .value {
            font-size: 1.8rem;
            color: #00aaff;
            font-weight: bold;
            .unit {
                font-size: 0.9rem;
                color: #c0c0c0;
                margin-left: 0.2rem;
            }
        }
    }
}
</style>