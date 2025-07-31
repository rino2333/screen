<template>
  <div class="dashboard">
    <!-- 头部区域 -->
    <header class="header">
      <div class="header-left">
        <button class="back-btn"><< 返回</button>
        <div class="weather">
          <span class="weather-icon">☁️🌧️</span>
          <span class="weather-text">大雨</span>
          <span class="temperature">17-28°C</span>
        </div>
        <div class="datetime">2021.12.02 星期三 15:20:33</div>
      </div>
      
      <div class="header-center">
        <h1 class="main-title">建筑物通信基础设施维护管理平台</h1>
      </div>
      
      <div class="header-right">
        <button class="nav-btn active">监控总览</button>
        <button class="nav-btn">资产监控</button>
        <button class="nav-btn">告警监控</button>
        <button class="nav-btn">视频监控</button>
      </div>
    </header>

    <!-- 主要内容区域 -->
    <main class="main-content">
      <!-- 左侧面板 - 资产监控区域 -->
      <div class="left-panel">
        <div class="panel-header">
          <button class="tab-btn active">资产监控区域</button>
          <button class="tab-btn">巡检监控区域</button>
        </div>
        
        <!-- 资产分布 -->
        <div class="section">
          <h3>资产分布</h3>
          <div class="chart-container">
            <div class="donut-chart">
              <div class="donut-segment type1"></div>
              <div class="donut-segment type2"></div>
              <div class="donut-segment type3"></div>
              <div class="donut-center">
                <span class="total-count">645</span>
                <span class="total-label">总数</span>
              </div>
            </div>
            <div class="chart-legend">
              <div class="legend-item">
                <span class="legend-color type1"></span>
                <span>类型一</span>
                <span class="count">215个</span>
              </div>
              <div class="legend-item">
                <span class="legend-color type2"></span>
                <span>类型二</span>
                <span class="count">215个</span>
              </div>
              <div class="legend-item">
                <span class="legend-color type3"></span>
                <span>类型三</span>
                <span class="count">215个</span>
              </div>
            </div>
          </div>
          <div class="filter-buttons">
            <button class="filter-btn active">设备类型</button>
            <button class="filter-btn">运营商</button>
            <button class="filter-btn">区域</button>
          </div>
        </div>

        <!-- 设备状态统计 -->
        <div class="section">
          <h3>设备状态统计</h3>
          <div class="status-cards">
            <div class="status-card">
              <div class="status-icon normal">✓</div>
              <div class="status-count">2195个</div>
              <div class="status-label">正常设备</div>
            </div>
            <div class="status-card">
              <div class="status-icon fault">!</div>
              <div class="status-count">2195个</div>
              <div class="status-label">故障设备</div>
            </div>
            <div class="status-card">
              <div class="status-icon maintenance">🔧</div>
              <div class="status-count">2195个</div>
              <div class="status-label">维修设备</div>
            </div>
            <div class="status-card">
              <div class="status-icon offline">🔌</div>
              <div class="status-count">2195个</div>
              <div class="status-label">离线设备</div>
            </div>
          </div>
        </div>

        <!-- 资产利用率 -->
        <div class="section">
          <h3>资产利用率</h3>
          <div class="utilization-bars">
            <div class="utilization-item">
              <div class="utilization-label">端口利用率</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: 89%"></div>
              </div>
              <div class="utilization-percent">89%</div>
            </div>
            <div class="utilization-item">
              <div class="utilization-label">机房利用率</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: 79%"></div>
              </div>
              <div class="utilization-percent">79%</div>
            </div>
            <div class="utilization-item">
              <div class="utilization-label">设备利用率</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: 80%"></div>
              </div>
              <div class="utilization-percent">80%</div>
            </div>
          </div>
        </div>

        <!-- 趋势图表 -->
        <div class="section">
          <div class="chart-tabs">
            <button class="chart-tab active">资产增长趋势</button>
            <button class="chart-tab">故障率趋势</button>
            <button class="chart-tab">利用率变化</button>
          </div>
          <div class="trend-chart">
            <canvas ref="leftTrendChart" width="300" height="150"></canvas>
          </div>
        </div>
      </div>

      <!-- 中央面板 - 全局视图 -->
      <div class="center-panel">
        <div class="globe-container">
          <div class="globe">
            <div class="globe-wireframe"></div>
            <div class="globe-glow"></div>
          </div>
        </div>
        
        <div class="data-cards">
          <div class="data-card">
            <div class="data-title">标题名称</div>
            <div class="data-value">17,369</div>
          </div>
          <div class="data-card">
            <div class="data-title">标题名称</div>
            <div class="data-value">17,369</div>
          </div>
          <div class="data-card">
            <div class="data-title">标题名称</div>
            <div class="data-value">17,369</div>
          </div>
          <div class="data-card">
            <div class="data-title">标题名称</div>
            <div class="data-value">17,369</div>
          </div>
        </div>

        <!-- 告警提示弹窗 -->
        <div class="alarm-popup">
          <div class="alarm-header">
            <span>告警提示</span>
            <button class="close-btn">×</button>
          </div>
          <div class="alarm-content">
            <div class="urgent-alarm">紧急告警数量: 21</div>
            <div class="alarm-types">
              <div class="alarm-type urgent">
                <span class="alarm-color"></span>
                <span>紧急告警</span>
                <span class="alarm-count">215个</span>
              </div>
              <div class="alarm-type prompt">
                <span class="alarm-color"></span>
                <span>提示告警</span>
                <span class="alarm-count">215个</span>
              </div>
              <div class="alarm-type important">
                <span class="alarm-color"></span>
                <span>重要告警</span>
                <span class="alarm-count">215个</span>
              </div>
              <div class="alarm-type general">
                <span class="alarm-color"></span>
                <span>一般告警</span>
                <span class="alarm-count">215个</span>
              </div>
            </div>
            <div class="latest-alarm">最新告警信息: 有1条紧急告警</div>
          </div>
        </div>
      </div>

      <!-- 右侧面板 - 工单监控区域 -->
      <div class="right-panel">
        <div class="panel-header">
          <button class="tab-btn active">工单监控区域</button>
          <button class="tab-btn">告警监控区域</button>
        </div>
        
        <!-- 工单状态分布 -->
        <div class="section">
          <h3>工单状态分布</h3>
          <div class="chart-container">
            <div class="donut-chart work-order">
              <div class="donut-segment pending"></div>
              <div class="donut-segment in-progress"></div>
              <div class="donut-segment completed"></div>
              <div class="donut-segment closed"></div>
              <div class="donut-center">
                <span class="total-count">860</span>
                <span class="total-label">总数</span>
              </div>
            </div>
            <div class="chart-legend">
              <div class="legend-item">
                <span class="legend-color pending"></span>
                <span>待处理</span>
                <span class="count">215个</span>
              </div>
              <div class="legend-item">
                <span class="legend-color in-progress"></span>
                <span>处理中</span>
                <span class="count">215个</span>
              </div>
              <div class="legend-item">
                <span class="legend-color completed"></span>
                <span>已完成</span>
                <span class="count">215个</span>
              </div>
              <div class="legend-item">
                <span class="legend-color closed"></span>
                <span>已关闭</span>
                <span class="count">215个</span>
              </div>
            </div>
          </div>
        </div>

        <!-- 工单类型统计 -->
        <div class="section">
          <h3>工单类型统计</h3>
          <div class="work-order-cards">
            <div class="work-order-card">
              <div class="work-order-icon">🔧</div>
              <div class="work-order-count">2195</div>
              <div class="work-order-label">故障工单</div>
            </div>
            <div class="work-order-card">
              <div class="work-order-icon">🔧</div>
              <div class="work-order-count">2195</div>
              <div class="work-order-label">维修工单</div>
            </div>
            <div class="work-order-card">
              <div class="work-order-icon">🔍</div>
              <div class="work-order-count">2195</div>
              <div class="work-order-label">巡检工单</div>
            </div>
            <div class="work-order-card">
              <div class="work-order-icon">📋</div>
              <div class="work-order-count">2195</div>
              <div class="work-order-label">其他工单</div>
            </div>
          </div>
        </div>

        <!-- 处理时效分析 -->
        <div class="section">
          <h3>处理时效分析</h3>
          <div class="efficiency-cards">
            <div class="efficiency-card">
              <div class="efficiency-label">平均处理时间</div>
              <div class="efficiency-value">31分钟</div>
            </div>
            <div class="efficiency-card">
              <div class="efficiency-label">超时工单数</div>
              <div class="efficiency-value">127</div>
            </div>
            <div class="efficiency-card">
              <div class="efficiency-label">及时完成率</div>
              <div class="efficiency-value">86%</div>
            </div>
          </div>
        </div>

        <!-- 工单趋势图 -->
        <div class="section">
          <div class="chart-tabs">
            <button class="chart-tab active">工单数量趋势</button>
            <button class="chart-tab">处理效率趋势</button>
            <button class="chart-tab">满意度趋势</button>
          </div>
          <div class="trend-chart">
            <canvas ref="rightTrendChart" width="300" height="150"></canvas>
          </div>
        </div>
      </div>
    </main>

    <!-- 底部状态栏 -->
    <footer class="footer">
      <div class="footer-left">系统运行状态: 正常</div>
      <div class="footer-center">网络连接状态: 正常</div>
      <div class="footer-right">数据更新时间: 2072/07/04 01:04</div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue'

const leftTrendChart = ref<HTMLCanvasElement>()
const rightTrendChart = ref<HTMLCanvasElement>()

onMounted(() => {
  drawTrendChart(leftTrendChart.value!, '#4A90E2')
  drawTrendChart(rightTrendChart.value!, '#50C878')
})

function drawTrendChart(canvas: HTMLCanvasElement, color: string) {
  const ctx = canvas.getContext('2d')!
  const width = canvas.width
  const height = canvas.height
  
  // 绘制网格
  ctx.strokeStyle = 'rgba(255, 255, 255, 0.1)'
  ctx.lineWidth = 1
  
  // 垂直网格线
  for (let i = 0; i <= 12; i++) {
    ctx.beginPath()
    ctx.moveTo((width / 12) * i, 0)
    ctx.lineTo((width / 12) * i, height)
    ctx.stroke()
  }
  
  // 水平网格线
  for (let i = 0; i <= 4; i++) {
    ctx.beginPath()
    ctx.moveTo(0, (height / 4) * i)
    ctx.lineTo(width, (height / 4) * i)
    ctx.stroke()
  }
  
  // 绘制趋势线
  ctx.strokeStyle = color
  ctx.lineWidth = 2
  ctx.beginPath()
  
  const points = [
    { x: 0, y: height * 0.7 },
    { x: width * 0.2, y: height * 0.5 },
    { x: width * 0.4, y: height * 0.3 },
    { x: width * 0.6, y: height * 0.6 },
    { x: width * 0.8, y: height * 0.4 },
    { x: width, y: height * 0.2 }
  ]
  
  ctx.moveTo(points[0].x, points[0].y)
  for (let i = 1; i < points.length; i++) {
    ctx.lineTo(points[i].x, points[i].y)
  }
  ctx.stroke()
  
  // 填充区域
  ctx.fillStyle = color + '20'
  ctx.beginPath()
  ctx.moveTo(points[0].x, height)
  for (let i = 0; i < points.length; i++) {
    ctx.lineTo(points[i].x, points[i].y)
  }
  ctx.lineTo(points[points.length - 1].x, height)
  ctx.closePath()
  ctx.fill()
}
</script>

<style scoped>
.dashboard {
  min-height: 100vh;
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
  color: white;
  font-family: 'Microsoft YaHei', Arial, sans-serif;
  position: relative;
  overflow: hidden;
}

.dashboard::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 40% 40%, rgba(120, 219, 255, 0.2) 0%, transparent 50%);
  pointer-events: none;
}

/* 头部样式 */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  position: relative;
  z-index: 10;
}

.header-left {
  display: flex;
  align-items: center;
  gap: 20px;
}

.back-btn {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
  padding: 8px 15px;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s;
}

.back-btn:hover {
  background: rgba(255, 255, 255, 0.2);
  box-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
}

.weather {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 14px;
}

.weather-icon {
  font-size: 16px;
}

.datetime {
  font-size: 14px;
  color: #ccc;
}

.header-center {
  flex: 1;
  text-align: center;
}

.main-title {
  font-size: 24px;
  font-weight: bold;
  background: linear-gradient(45deg, #4A90E2, #50C878);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-shadow: 0 0 20px rgba(74, 144, 226, 0.5);
  margin: 0;
}

.header-right {
  display: flex;
  gap: 15px;
}

.nav-btn {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s;
}

.nav-btn.active,
.nav-btn:hover {
  background: linear-gradient(45deg, #4A90E2, #50C878);
  box-shadow: 0 0 15px rgba(74, 144, 226, 0.5);
}

/* 主要内容区域 */
.main-content {
  display: flex;
  height: calc(100vh - 140px);
  padding: 20px;
  gap: 20px;
}

.left-panel,
.right-panel {
  width: 350px;
  background: rgba(0, 0, 0, 0.6);
  border-radius: 10px;
  padding: 20px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  overflow-y: auto;
}

.center-panel {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
}

/* 面板头部 */
.panel-header {
  display: flex;
  margin-bottom: 20px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  padding-bottom: 10px;
}

.tab-btn {
  background: none;
  border: none;
  color: #ccc;
  padding: 8px 15px;
  cursor: pointer;
  transition: all 0.3s;
  border-radius: 5px;
}

.tab-btn.active {
  background: linear-gradient(45deg, #4A90E2, #50C878);
  color: white;
}

/* 章节样式 */
.section {
  margin-bottom: 25px;
  padding: 15px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.section h3 {
  margin: 0 0 15px 0;
  font-size: 16px;
  color: #4A90E2;
}

/* 图表容器 */
.chart-container {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 15px;
}

/* 环形图 */
.donut-chart {
  position: relative;
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: conic-gradient(
    #FFD700 0deg 120deg,
    #50C878 120deg 240deg,
    #4A90E2 240deg 360deg
  );
  display: flex;
  align-items: center;
  justify-content: center;
}

.donut-chart.work-order {
  background: conic-gradient(
    #FFD700 0deg 90deg,
    #50C878 90deg 180deg,
    #4A90E2 180deg 270deg,
    #87CEEB 270deg 360deg
  );
}

.donut-center {
  background: #1a1a2e;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.total-count {
  font-size: 18px;
  font-weight: bold;
  color: #4A90E2;
}

.total-label {
  font-size: 12px;
  color: #ccc;
}

/* 图例 */
.chart-legend {
  flex: 1;
}

.legend-item {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 8px;
  font-size: 14px;
}

.legend-color {
  width: 12px;
  height: 12px;
  border-radius: 2px;
}

.legend-color.type1 { background: #FFD700; }
.legend-color.type2 { background: #50C878; }
.legend-color.type3 { background: #4A90E2; }
.legend-color.pending { background: #FFD700; }
.legend-color.in-progress { background: #50C878; }
.legend-color.completed { background: #4A90E2; }
.legend-color.closed { background: #87CEEB; }

.count {
  color: #4A90E2;
  font-weight: bold;
}

/* 筛选按钮 */
.filter-buttons {
  display: flex;
  gap: 10px;
}

.filter-btn {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
  padding: 5px 10px;
  border-radius: 3px;
  cursor: pointer;
  font-size: 12px;
  transition: all 0.3s;
}

.filter-btn.active {
  background: #4A90E2;
  border-color: #4A90E2;
}

/* 状态卡片 */
.status-cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.status-card {
  background: rgba(255, 255, 255, 0.05);
  padding: 15px;
  border-radius: 8px;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.status-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 10px;
  font-size: 18px;
  font-weight: bold;
}

.status-icon.normal {
  background: #50C878;
  color: white;
}

.status-icon.fault {
  background: #FF6B6B;
  color: white;
}

.status-icon.maintenance {
  background: #FFD700;
  color: #333;
}

.status-icon.offline {
  background: #6C757D;
  color: white;
}

.status-count {
  font-size: 18px;
  font-weight: bold;
  color: #4A90E2;
  margin-bottom: 5px;
}

.status-label {
  font-size: 12px;
  color: #ccc;
}

/* 利用率条 */
.utilization-bars {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.utilization-item {
  display: flex;
  align-items: center;
  gap: 15px;
}

.utilization-label {
  width: 80px;
  font-size: 14px;
  color: #ccc;
}

.progress-bar {
  flex: 1;
  height: 8px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #4A90E2, #50C878);
  border-radius: 4px;
  transition: width 0.3s ease;
}

.utilization-percent {
  width: 40px;
  text-align: right;
  font-size: 14px;
  color: #4A90E2;
  font-weight: bold;
}

/* 趋势图表 */
.chart-tabs {
  display: flex;
  gap: 10px;
  margin-bottom: 15px;
}

.chart-tab {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: #ccc;
  padding: 5px 10px;
  border-radius: 3px;
  cursor: pointer;
  font-size: 12px;
  transition: all 0.3s;
}

.chart-tab.active {
  background: #4A90E2;
  color: white;
}

.trend-chart {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  padding: 10px;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

/* 中央面板 */
.globe-container {
  position: relative;
  width: 300px;
  height: 300px;
  margin-bottom: 30px;
}

.globe {
  position: relative;
  width: 100%;
  height: 100%;
}

.globe-wireframe {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 200px;
  height: 200px;
  border: 2px solid #4A90E2;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(74, 144, 226, 0.1) 0%, transparent 70%);
  animation: rotate 20s linear infinite;
}

.globe-wireframe::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 150px;
  height: 150px;
  border: 1px solid rgba(74, 144, 226, 0.5);
  border-radius: 50%;
}

.globe-wireframe::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100px;
  height: 100px;
  border: 1px solid rgba(74, 144, 226, 0.3);
  border-radius: 50%;
}

.globe-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 250px;
  height: 250px;
  background: radial-gradient(circle, rgba(74, 144, 226, 0.3) 0%, transparent 70%);
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite alternate;
}

@keyframes rotate {
  from { transform: translate(-50%, -50%) rotate(0deg); }
  to { transform: translate(-50%, -50%) rotate(360deg); }
}

@keyframes pulse {
  from { opacity: 0.5; transform: translate(-50%, -50%) scale(1); }
  to { opacity: 1; transform: translate(-50%, -50%) scale(1.1); }
}

/* 数据卡片 */
.data-cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin-bottom: 30px;
}

.data-card {
  background: rgba(255, 255, 255, 0.05);
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s;
}

.data-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(74, 144, 226, 0.3);
}

.data-title {
  font-size: 14px;
  color: #ccc;
  margin-bottom: 10px;
}

.data-value {
  font-size: 24px;
  font-weight: bold;
  color: #4A90E2;
}

/* 告警弹窗 */
.alarm-popup {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  background: rgba(0, 0, 0, 0.9);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  padding: 20px;
  min-width: 400px;
  backdrop-filter: blur(10px);
}

.alarm-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
  padding-bottom: 10px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.close-btn {
  background: none;
  border: none;
  color: #ccc;
  font-size: 20px;
  cursor: pointer;
  padding: 0;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: all 0.3s;
}

.close-btn:hover {
  background: rgba(255, 255, 255, 0.1);
  color: white;
}

.urgent-alarm {
  font-size: 16px;
  color: #FF6B6B;
  font-weight: bold;
  margin-bottom: 15px;
}

.alarm-types {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-bottom: 15px;
}

.alarm-type {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 14px;
}

.alarm-color {
  width: 12px;
  height: 12px;
  border-radius: 2px;
}

.alarm-color.urgent { background: #FFD700; }
.alarm-color.prompt { background: #50C878; }
.alarm-color.important { background: #FF6B6B; }
.alarm-color.general { background: #87CEEB; }

.alarm-count {
  color: #4A90E2;
  font-weight: bold;
}

.latest-alarm {
  font-size: 14px;
  color: #ccc;
}

/* 工单卡片 */
.work-order-cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.work-order-card {
  background: rgba(255, 255, 255, 0.05);
  padding: 15px;
  border-radius: 8px;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.work-order-icon {
  font-size: 24px;
  margin-bottom: 10px;
}

.work-order-count {
  font-size: 18px;
  font-weight: bold;
  color: #4A90E2;
  margin-bottom: 5px;
}

.work-order-label {
  font-size: 12px;
  color: #ccc;
}

/* 效率卡片 */
.efficiency-cards {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.efficiency-card {
  background: rgba(255, 255, 255, 0.05);
  padding: 15px;
  border-radius: 8px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.efficiency-label {
  font-size: 14px;
  color: #ccc;
}

.efficiency-value {
  font-size: 16px;
  font-weight: bold;
  color: #4A90E2;
}

/* 底部状态栏 */
.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(10px);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  font-size: 14px;
  color: #ccc;
}

/* 响应式设计 */
@media (max-width: 1200px) {
  .main-content {
    flex-direction: column;
    height: auto;
  }
  
  .left-panel,
  .right-panel {
    width: 100%;
  }
  
  .center-panel {
    order: -1;
    margin-bottom: 20px;
  }
}

/* 滚动条样式 */
::-webkit-scrollbar {
  width: 6px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 3px;
}

::-webkit-scrollbar-thumb {
  background: rgba(74, 144, 226, 0.5);
  border-radius: 3px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(74, 144, 226, 0.7);
}
</style>