<template>
  <div class="panel">
    <h2 v-if="title" class="panel-title">{{ title }}</h2>
    <div class="panel-content">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
});
</script>

<style lang="scss" scoped>
.panel {
  background-color: rgba(10, 25, 50, 0.4);
  border: 1px solid rgba(29, 90, 142, 0.5);
  border-radius: 4px;
  backdrop-filter: blur(5px);
  height: 100%;
  display: flex;
  flex-direction: column;

  .panel-title {
    font-size: 1.1rem;
    color: #ffffff;
    margin: 0;
    padding: 0.8rem 1rem;
    border-bottom: 1px solid rgba(29, 90, 142, 0.8);
    font-weight: 500;
    text-shadow: 0 0 5px rgba(0, 170, 255, 0.5);
  }

  .panel-content {
    flex-grow: 1;
    overflow: hidden;
    padding: 1rem;
  }
}
</style>