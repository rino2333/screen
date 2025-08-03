<template>
  <div class="app-container">
    <MainHeader />
    <main class="main-content">
      <LeftPanel />
      <CenterPanel />
      <RightPanel />
    </main>
  </div>
</template>

<script setup>
import MainHeader from './components/layout/MainHeader.vue';
import LeftPanel from './components/layout/LeftPanel.vue';
import CenterPanel from './components/layout/CenterPanel.vue';
import RightPanel from './components/layout/RightPanel.vue';
</script>

<style lang="scss">
.app-container {
  background: #030f23;
  color: #c0c0c0;
  min-height: 100vh;
  padding: 1rem;
}

.main-content {
  display: grid;
  grid-template-columns: 24% 48% 28%;
  gap: 1rem;
  margin-top: 1rem;
}
</style>